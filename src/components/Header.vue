<template>
  <header class="header">
    <router-link to="/" class="header__logo">logo</router-link>
    <nav class="header__nav">
      <ul class="header__nav-list">
        <li
          v-for="item in navList"
          :key="item.title"
          class="header__nav-item"
        >
          <router-link :to="item.path" class="header__nav-link">
            <IconSvg
              v-if="item.icon"
              :icon="item.icon"
            />
            <p>{{ item.title }}</p>
          </router-link>
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
          path: "/about",
          title: "about"
        },
        {
          path: "/",
          icon: {
            name: "user",
            width: "11",
            height: "15",
          },
          title: "team"
        },
        {
          path: "/work",
          icon: {
            name: "menu",
            width: "15",
            height: "15",
          },
          title: "work"
        },
        {
          path: "/pricing",
          icon: {
            name: "dollar",
            width: "15",
            height: "16",
          },
          title: "pricing"
        },
        {
          path: "/contact",
          icon: {
            name: "mail",
            width: "15",
            height: "15",
          },
          title: "contact"
        },
      ]
    }
  }
}
</script>
