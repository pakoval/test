<template>
  <footer class="footer">
    <Button name="footer" @click="scrollToTop">
      <IconSvg :icon="iconToTop"/>
      To the top
    </Button>
    <div class="footer__social">
      <a
        v-for="icon in socialIcons"
        :key="icon.name"
        :href="icon.link"
      >
        <IconSvg :icon="icon"/>
      </a>
    </div>
    <p class="copyright">Powered by Pakoval</p>
  </footer>
</template>

<script>
import Button from "@/components/Button.vue";
import IconSvg from "@/components/IconSvg.vue";

export default {
  name: "FooterBlock",
  components: {
    IconSvg,
    Button,
  },
  data() {
    return {
      socialIcons: [
        {
          link: "/",
          name: "inst",
          width: "20",
          height: "20",
        },
        {
          link: "#",
          name: "linkedin",
          width: "20",
          height: "20",
        },
        {
          link: "#",
          name: "git",
          width: "20",
          height: "20",
        },
      ],
      iconToTop: {
        name: "arrow",
        width: "15",
        height: "15",
      },
    };
  },
  methods: {
    scrollToTop() {
      window.scrollTo({ top: 0, left: 0, behavior: 'smooth' });
    },
  },
}
</script>