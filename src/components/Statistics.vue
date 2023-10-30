<template>
  <section class="statistics">
    <div
      v-for="(item, i) in statistics"
      :key="i"
      class="statistics__item"
    >
      <p class="statistics__item-num">{{ item.num }}+</p>
      <p class="statistics__item-title">{{ item.title }}</p>
    </div>
  </section>
</template>

<script>
export default {
  name: "StatisticsBlock",
  data() {
    return {
      statistics: [
        {
          num: 14,
          title: "partners"
        },
        {
          num: 55,
          title: "Projects Done"
        },
        {
          num: 89,
          title: "happy clients"
        },

        {
          num: 154,
          title: "Meetings"
        },
      ],
    }
  }
}
</script>