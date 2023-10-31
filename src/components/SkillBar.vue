<template>
  <div class="skillbar">
    <div class="skillbar__top">
      <IconSvg :icon="skill.icon"/>
      <p class="skillbar__title">{{ skill.title }}</p>
    </div>

    <div class="skillbar__progress">
      <div :style="setProgressBar" class="skillbar__progress--filled">
        <p class="skillbar__progress-percent">{{ skill.percent }}%</p>
      </div>
    </div>
  </div>
</template>

<script>
import IconSvg from "@/components/IconSvg.vue";

export default {
  name: "SkillBar",
  components: {
    IconSvg
  },
  props: {
    skill: {
      type: Object,
      default: () => {},
    },
  },
  computed: {
    setProgressBar() {
      return { width: this.skill.percent + "%" }
    }
  }
}
</script>
