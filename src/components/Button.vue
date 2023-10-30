<template>
  <button
    :type="type"
    class="btn"
    :class="name ? [`btn--${name}`] : null"
    @click="handleClick"
  >
    <slot/>
  </button>
</template>

<script>
export default {
  name: "BaseButton",
  props: {
    name: {
      type: String,
    },
    type: {
      type: String,
      default: () => null,
    },
  },
  methods: {
    handleClick() {
      this.$emit("click")
    }
  }
}
</script>
