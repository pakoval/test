<template>
  <header class="header">
    <router-link to="/" class="header__logo">logo</router-link>
    <nav class="header__nav">
      <ul class="header__nav-list">
        <li
          v-for="item in navList"
          :key="item.id"
          class="header__nav-item"
          @click="scrollToSection(item.id)"
        >
          <IconSvg
            v-if="item.icon"
            :icon="item.icon"
          />
          <p>{{ item.title }}</p>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
import IconSvg from "@/components/IconSvg.vue";
export default {
  name: 'HeaderBlock',
  components: {
    IconSvg,
  },
  data() {
    return {
      navList: [
        {
          id: "about",
          title: "about"
        },
        {
          id: "team",
          icon: {
            name: "user",
            width: "11",
            height: "15",
          },
          title: "team"
        },
        {
          id: "portfolio",
          icon: {
            name: "menu",
            width: "15",
            height: "15",
          },
          title: "work"
        },
        {
          id: "pricing",
          icon: {
            name: "dollar",
            width: "15",
            height: "16",
          },
          title: "pricing"
        },
        {
          id: "contact",
          icon: {
            name: "mail",
            width: "15",
            height: "15",
          },
          title: "contact"
        },
      ]
    };
  },
  methods: {
    scrollToSection(id) {
      const section = document.getElementById(id);
      section.scrollIntoView({ behavior: 'smooth' });
    }
  }
}
</script>
