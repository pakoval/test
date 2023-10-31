<template>
  <header class="header">
    <router-link to="/" class="header__logo">logo</router-link>

    <input type="checkbox" id="check">
    <label for="check" class="header__mobile">
      <IconSvg :icon="iconMobile" id="mobile-menu"/>
      <IconSvg :icon="iconMobileClose" id="mobile-close"/>
    </label>

    <nav class="header__nav">
      <ul class="header__nav-list">
        <li
          v-for="item in navList"
          :key="item.id"
          class="header__nav-item"
          @click="scrollToSection(item.id); uncheckMenu()"
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
      ],
      iconMobile: {
        name: "menu-mobile",
        width: "32",
        height: "32",
      },
      iconMobileClose: {
        name: "close",
        width: "32",
        height: "32",
      }
    };
  },
  methods: {
    scrollToSection(id) {
      const section = document.getElementById(id);
      section.scrollIntoView({ behavior: "smooth" });
    },
    uncheckMenu() {
      const check = document.getElementById("check");
      if(check.checked) {
        check.checked = false
      }
    }
  }
}
</script>
