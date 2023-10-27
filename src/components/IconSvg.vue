<template>
  <svg
  class="icon"
  :class="[`icon-${iconName}`, customClass]"
  :width="width"
  :height="height"
  >
    <use :xlink:href="`/sprite.svg#${iconName}`"></use>
  </svg>
</template>

<script>
export default {
  name: "IconSvg",
  props: {
    iconName: {
      type: String,
      default: "i",
    },
    customClass: {
      type: String,
      default: "",
    },
    width: {
      type: [Number, String],
      default: "16",
    },
    height: {
      type: [Number, String],
      default: "16",
    }
  }
}
</script>
