<template>
  <svg
    v-if="icon"
    class="icon"
    :class="setIconClass"
    :width="icon.width"
    :height="icon.height"
  >
    <use :xlink:href="`/sprite.svg#${icon.name}`"></use>
  </svg>
</template>

<script>
export default {
  name: "IconSvg",
  props: {
    icon: {
      type: Object,
      required: false,
      default: () => {},
    },
  },
  computed: {
    setIconClass() {
      return [`icon-${this.icon.name}`]
    }
  }
}
</script>
