<template>
  <div class="pricing-card">
    <p
      class="pricing-card__title"
      :class="tariff.isHot ? 'pricing-card__title--hot': null"
    >
      {{ tariff.title }}
    </p>
    <ul class="pricing-card__list">
      <li
        v-for="(item, i) in tariff.advantages"
        :key="i"
        class="pricing-card__item"
      >
        {{ item }}
      </li>
    </ul>
    <p class="pricing-card__price">
      $ {{ tariff.price }}
      <span class="pricing-card__type">{{ tariff.type }}</span>
    </p>
    <div class="pricing-card__bottom">
      <Button name="pricing">Sign Up</Button>
    </div>
  </div>
</template>

<script>
import Button from "@/components/Button.vue";

export default {
  name: "PricingCard",
  components: {
    Button,
  },
  props: {
    tariff: {
      type: Object,
      default: () => {},
    },
  },
}
</script>
