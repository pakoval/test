<template>
  <button class="btn" :class="name ? [`btn--${name}`] : null">
    <slot/>
  </button>
</template>

<script>
export default {
  name: "BaseButton",
  props: {
    name: {
      type: String,
    }
  }
}
</script>
