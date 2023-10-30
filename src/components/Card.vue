<template>
  <div class="card">
    <div class="card__picture">
      <img :src="require(`@/assets/img/${worker.img}`)" :alt="worker.img" />
    </div>
    <div class="card__info">
      <h3 class="card__info-name">{{ worker.name }}</h3>
      <p class="card__info-post">{{ worker.position }}</p>
      <p class="card__info-summary">{{ worker.summary }}</p>
      <Button class="card__info-btn" name="card">
        <IconSvg :icon="icon" />
        Contact
      </Button>
    </div>
  </div>
</template>

<script>
import Button from "@/components/Button.vue"
import IconSvg from "@/components/IconSvg.vue";

export default {
  name: "CardBlock",
  components: {
    Button,
    IconSvg,
  },
  props: {
    worker: {
      type: Object,
      default: () => {},
    }
  },
  data() {
    return {
      icon: {
        name: "mail",
        width: "15",
        height: "15",
      },
    }
  }
}
</script>
