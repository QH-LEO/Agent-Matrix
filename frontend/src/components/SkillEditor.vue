<script setup>
defineProps({
  selectedPipeline: { type: Object, default: null },
  hasAgents: { type: Boolean, required: true },
  forms: { type: Object, required: true },
  availableAgentsForSkill: { type: Array, required: true },
  focusedAgent: { type: Object, default: null },
});

defineEmits([
  "add-default-skill",
  "set-default-skill-field",
  "delete-default-skill",
  "add-skill",
  "focus-stage",
  "focus-agent",
  "delete-skill",
  "set-skill-field",
]);
</script>

<template>
  <div class="panel-section skill-section">
    <div v-if="!selectedPipeline" class="panel-empty">请先创建或选择一条流水线。</div>
    <template v-else>
      <div class="section-heading">
        <p>Skill 装配</p>
        <span>全局默认 Skill 会自动注入所有 Agent；专属 Skill 只绑定当前 Agent。</span>
      </div>

      <div class="toolbar-group selection-card">
        <div class="section-heading tight">
          <p>全局默认 Skill</p>
          <span>所有 Agent 编译时都会继承这里的 Skill 目录。</span>
        </div>
        <div class="stack-form">
          <div class="inline-form">
            <input v-model="forms.defaultSkillName" type="text" placeholder="Skill 名称，可留空从目录名推断" />
            <input v-model="forms.defaultSkillVersion" class="version-input" type="text" />
          </div>
          <input
            v-model="forms.defaultSkillPath"
            type="text"
            placeholder="全局 Skill 目录，例如：.claude/skills/using-agentflow"
          />
          <button class="indigo-button" type="button" @click="$emit('add-default-skill')">添加全局默认 Skill</button>
        </div>

        <div class="skill-directory-list">
          <article v-for="skill in selectedPipeline.defaultSkills || []" :key="skill.id" class="skill-directory-card active">
            <div class="card-header-actions">
              <strong>{{ skill.name }} <small>v{{ skill.version }}</small></strong>
              <button class="ghost-button compact danger-button" type="button" @click="$emit('delete-default-skill', skill)">
                删除
              </button>
            </div>
            <label>
              <span>Skill 名称</span>
              <input
                :value="skill.name"
                type="text"
                @input="$emit('set-default-skill-field', skill, 'name', $event.target.value)"
              />
            </label>
            <label>
              <span>版本</span>
              <input
                :value="skill.version"
                type="text"
                @input="$emit('set-default-skill-field', skill, 'version', $event.target.value)"
              />
            </label>
            <label>
              <span>目录</span>
              <input
                :value="skill.path"
                type="text"
                @input="$emit('set-default-skill-field', skill, 'path', $event.target.value)"
              />
            </label>
          </article>
          <div v-if="!(selectedPipeline.defaultSkills || []).length" class="mini-empty">还没有全局默认 Skill。</div>
        </div>
      </div>

      <div v-if="!hasAgents" class="panel-empty">创建 Agent 后，可继续配置单个 Agent 的专属 Skill。</div>

      <div v-else class="stack-form">
        <div class="section-heading tight">
          <p>Agent 专属 Skill</p>
          <span>只给当前选择的 Agent 追加能力；不会影响其他 Agent。</span>
        </div>
        <select
          v-model="forms.skillStageId"
          @change="$emit('focus-stage', selectedPipeline.stages.find((stage) => stage.id === forms.skillStageId))"
        >
          <option value="" disabled>选择阶段</option>
          <option v-for="stage in selectedPipeline.stages" :key="stage.id" :value="stage.id">
            {{ stage.name }}
          </option>
        </select>
        <select
          v-model="forms.skillAgentId"
          @change="$emit('focus-agent', selectedPipeline.stages.find((stage) => stage.id === forms.skillStageId), availableAgentsForSkill.find((agent) => agent.id === forms.skillAgentId))"
        >
          <option value="" disabled>选择 Agent</option>
          <option v-for="agent in availableAgentsForSkill" :key="agent.id" :value="agent.id">
            {{ agent.name }}
          </option>
        </select>
        <div class="inline-form">
          <input v-model="forms.skillName" type="text" placeholder="Skill 名称，可留空从目录名推断" />
          <input v-model="forms.skillVersion" class="version-input" type="text" />
        </div>
        <input
          v-model="forms.skillPath"
          type="text"
          placeholder="Skill 目录，例如：.claude/skills/using-agentflow 或 ~/.claude/skills/xxx"
        />
        <div class="form-note">
          这里只保存目录引用，不在页面里编辑 SKILL.md；编译时会把全局默认 Skill 和当前 Agent 专属 Skill 一起写入 Agent 描述。
        </div>
        <button class="indigo-button" type="button" @click="$emit('add-skill')">绑定 Skill 目录</button>
      </div>

      <div v-if="hasAgents" class="toolbar-group selection-card">
        <div class="section-heading tight">
          <p>当前 Agent</p>
          <span>{{ focusedAgent ? focusedAgent.name : "未选择 Agent" }}</span>
        </div>

        <div v-if="focusedAgent" class="inspector-card">
          <strong>{{ focusedAgent.name }}</strong>
          <span>{{ focusedAgent.responsibility || "暂未填写职责" }}</span>
          <div class="skill-directory-list">
            <article v-for="skill in selectedPipeline.defaultSkills || []" :key="`default-${skill.id}`" class="skill-directory-card">
              <strong>{{ skill.name }} <small>v{{ skill.version }}</small></strong>
              <span>全局默认 · {{ skill.path || "未配置目录" }}</span>
            </article>
          </div>
          <div class="skill-directory-list">
            <article v-for="skill in focusedAgent.skills" :key="skill.id" class="skill-directory-card active">
              <div class="card-header-actions">
                <strong>{{ skill.name }} <small>v{{ skill.version }}</small></strong>
                <button class="ghost-button compact danger-button" type="button" @click="$emit('delete-skill', skill)">
                  删除
                </button>
              </div>
              <label>
                <span>Skill 名称</span>
                <input
                  :value="skill.name"
                  type="text"
                  @input="$emit('set-skill-field', skill, 'name', $event.target.value)"
                />
              </label>
              <label>
                <span>版本</span>
                <input
                  :value="skill.version"
                  type="text"
                  @input="$emit('set-skill-field', skill, 'version', $event.target.value)"
                />
              </label>
              <label>
                <span>目录</span>
                <input
                  :value="skill.path"
                  type="text"
                  @input="$emit('set-skill-field', skill, 'path', $event.target.value)"
                />
              </label>
            </article>
            <div v-if="!focusedAgent.skills.length" class="mini-empty">这个 Agent 还没有专属 Skill。</div>
          </div>
        </div>
      </div>
    </template>
  </div>
</template>
