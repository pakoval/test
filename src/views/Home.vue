<template>
  <div class="home">
    <Header/>
    <main>
      <section class="hero">
        <h1 class="hero__title">Start something that matters</h1>
        <p class="hero__subtitle">
          Stop wasting valuable time with projects that just isn't you
        </p>
        <router-link to="/" class="hero__link">Learn more and start today</router-link>

        <div class="hero__social">
          <router-link
            v-for="icon in socialIcons"
            :key="icon.name"
            :to="icon.link"
            class="hero__social-link"
          >
            <IconSvg :icon="icon"/>
          </router-link>
        </div>
      </section>

      <section class="features">
        <h3 class="title">about the company</h3>
        <p class="subtitle">Key features of our company</p>

        <div class="features__items">
          <div
            v-for="item in featureItems"
            :key="item.title"
            class="features__item"
          >
            <div class="features__item-icon">
              <IconSvg :icon="item.icon"/>
            </div>
            <p class="features__item-title">{{ item.title }}</p>
            <p class="features__item-desc">{{ item.description }}</p>
          </div>
        </div>
      </section>

      <section class="works">
          <div class="works__info">
            <h3 class="works__info-title">We know design</h3>
            <p class="works__info-desc">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
              tempor incididunt ut labore et dolore
            </p>
            <router-link to="/" class="works__info-link">
              <IconSvg :icon="workIcon" />
              View Our Works
            </router-link>
          </div>
          <div class="works__picture">
            <img src="@/assets/img/work-img.jpeg" alt="works" class="works__img" />
          </div>
      </section>

      <section class="team">
        <h3 class="title">the team</h3>
        <p class="subtitle">The ones who runs this company</p>

        <div class="team__gallery">
          <Card
            v-for="(worker) in workers"
            :key="worker.name"
            :worker="worker"
          />
        </div>
      </section>

      <Statistics/>

      <section class="portfolio">
        <h3 class="title">our work</h3>
        <p class="subtitle">What we've done for people</p>

        <div class="portfolio__gallery">
          <router-link
            v-for="(item, id) in portfolio"
            :key="id"
            to="#"
            class="portfolio__gallery-link"
          >
            <img
              :src="require(`@/assets/img/${item.img}`)"
              :alt="item.img"
              class="portfolio__gallery-img"
            />
          </router-link>

        </div>
      </section>
    </main>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import IconSvg from "@/components/IconSvg.vue";
import Card from "@/components/Card.vue";
import Statistics from "@/components/Statistics.vue";

export default {
  name: "HomeView",
  components: {
    Header,
    IconSvg,
    Card,
    Statistics,
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
      featureItems: [
        {
          title: "Responsive",
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore",
          icon: {
            name: "monitor",
            width: "50",
            height: "50",
          },
        },
        {
          title: "Passion",
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore",
          icon: {
            name: "heart",
            width: "50",
            height: "50",
          },
        },
        {
          title: "Design",
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore",
          icon: {
            name: "diamond",
            width: "50",
            height: "50",
          },
        },
        {
          title: "Support",
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore",
          icon: {
            name: "setting",
            width: "50",
            height: "50",
          },
        },
      ],
      workIcon: {
        name: "menu",
        width: "16",
        height: "16",
      },
      workers: [
        {
          img: "worker1.jpeg",
          name: "John Doe",
          position: "CEO",
          summary: "Phasellus eget enim eu lectus faucibus vestibulum. Suspendisse sodales pellentesque elementum"
        },
        {
          img: "worker2.jpeg",
          name: "Anja Doe",
          position: "Art Director",
          summary: "Phasellus eget enim eu lectus faucibus vestibulum. Suspendisse sodales pellentesque elementum"
        },
        {
          img: "worker3.jpeg",
          name: "Mike Ross",
          position: "Web Designer",
          summary: "Phasellus eget enim eu lectus faucibus vestibulum. Suspendisse sodales pellentesque elementum"
        },
        {
          img: "worker4.jpeg",
          name: "Dan Star",
          position: "Designer",
          summary: "Phasellus eget enim eu lectus faucibus vestibulum. Suspendisse sodales pellentesque elementum"
        },
      ],
      portfolio: [
        {
          img: "drone.jpeg",
          link: "#"
        },
        {
          img: "cam.jpeg",
          link: "#"
        },
        {
          img: "desk.jpeg",
          link: "#"
        },
        {
          img: "ios.jpeg",
          link: "#"
        },
        {
          img: "micro.jpeg",
          link: "#"
        },
        {
          img: "typewriter.jpeg",
          link: "#"
        },
        {
          img: "soundbox.jpeg",
          link: "#"
        },
        {
          img: "tableturner.jpeg",
          link: "#"
        },
      ]
    };
  },
}
</script>

<style lang="scss">
h1 {}
</style>
