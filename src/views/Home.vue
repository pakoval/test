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
          <a
            v-for="icon in socialIcons"
            :key="icon.name"
            :href="icon.link"
            class="hero__social-link"
          >
            <IconSvg :icon="icon"/>
          </a>
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
            v-for="worker in workers"
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

      <section class="skills">
        <div class="skills__info">
          <h3 class="skills__info-title">Our Skills</h3>
          <p class="skills__info-desc">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
            tempor incididunt ut labore et dolore
          </p>
        </div>

        <div class="skills__items">
          <SkillBar
            v-for="skill in skills"
            :key="skill.title"
            :skill="skill"
          />
        </div>
      </section>

      <section class="pricing">
        <h3 class="title">pricing</h3>
        <p class="subtitle">Choose a pricing plan that fits your needs</p>

        <div class="pricing__cards">
          <PricingCard
            v-for="tariff in pricingCards"
            :key="tariff.title"
            :tariff="tariff"
          />
        </div>
      </section>

      <section class="contact">
        <h3 class="title">contact</h3>
        <p class="subtitle">Lets get in touch. Send us a message</p>

        <ul class="contact__info">
          <li class="contact__info-item">
            <img src="@/assets/img/geo.png" alt="geo" class="contact__info-img">
            <a
              href="https://maps.app.goo.gl/syeLomec2tPBstiSA"
              target="_blank"
              class="contact__info-link"
            >
              Chicago, US
            </a>
          </li>
          <li class="contact__info-item">
            <img src="@/assets/img/phone.png" alt="phone" class="contact__info-img">
            <a href="tel:00151515" class="contact__info-link">
              Phone: +00 151515
            </a>
          </li>
          <li class="contact__info-item">
            <img src="@/assets/img/mail.png" alt="mail" class="contact__info-img">
            <a href="mailto:mail@mail.com" class="contact__info-link">
              Email: mail@mail.com
            </a>
          </li>
        </ul>

        <form
          class="contact-form"
          method="post"
          @submit.prevent="submitForm"
        >
          <input
            v-model="formData.name"
            type="text"
            placeholder="Name"
            required
            name="name"
            class="contact-form__input"
          >
          <input
            v-model="formData.email"
            type="email"
            placeholder="Email"
            required
            name="email"
            class="contact-form__input"
          >
          <input
            v-model="formData.subject"
            type="text"
            placeholder="Subject"
            required
            name="subject"
            class="contact-form__input"
          >
          <textarea
            v-model="formData.message"
            placeholder="Message"
            class="contact-form__textarea"
          ></textarea>
          <Button type="submit" name="form">
            <IconSvg :icon="iconForm" />
            Send Message
          </Button>
        </form>

        <img src="@/assets/img/map.jpg" alt="map" class="contact__map-img">
      </section>
    </main>
    <Footer/>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import IconSvg from "@/components/IconSvg.vue";
import Card from "@/components/Card.vue";
import Statistics from "@/components/Statistics.vue";
import SkillBar from "@/components/SkillBar.vue";
import PricingCard from "@/components/PricingCard.vue";
import Button from "@/components/Button.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "HomeView",
  components: {
    Footer,
    Button,
    PricingCard,
    Header,
    IconSvg,
    Card,
    Statistics,
    SkillBar,
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
      ],
      skills: [
        {
          title: "Photography",
          percent: 90,
          icon: {
            name: "camera",
            width: "18",
            height: "18",
          },
        },
        {
          title: "Web design",
          percent: 85,
          icon: {
            name: "design",
            width: "18",
            height: "18",
          },
        },
        {
          title: "Development",
          percent: 75,
          icon: {
            name: "development",
            width: "18",
            height: "18",
          },
        },
      ],
      pricingCards: [
        {
          title: "Basic",
          advantages: ["10GB Storage", "10 Emails", "10 Domains", "Endless Support"],
          price: 10,
          isHot: false,
          type: "per month",
        },
        {
          title: "Pro",
          advantages: ["25GB Storage", "25 Emails", "25 Domains", "Endless Support"],
          price: 20,
          isHot: true,
          type: "per month",
        },
        {
          title: "Premium",
          advantages: ["50GB Storage", "50 Emails", "65 Domains", "Endless Support"],
          price: 50,
          isHot: false,
          type: "per month",
        },
      ],
      iconForm: {
        name: "send",
        width: "15",
        height: "15",
      },
      formData: {
        name: "",
        email: "",
        subject: "",
        message: "",
      },
    };
  },
  methods: {
    submitForm() {
      console.log(this.formData)
    },
  }
}
</script>

<style lang="scss">
h1 {}
</style>
