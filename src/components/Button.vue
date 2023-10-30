<template>
  <button
    :type="type"
    class="btn"
    :class="setBtnClass"
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
  },
  computed: {
    setBtnClass() {
      return this.name ? [`btn--${this.name}`] : null
    }
  }
}
</script>
