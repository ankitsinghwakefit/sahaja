<template>
  <div class="parent-container">
    <b-navbar toggleable="lg" type="dark" variant="info">
      <b-navbar-brand to="/" class="mr-4"
        ><img src="../images/swastika.png" fluid alt="swastika"
      /></b-navbar-brand>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item
            v-for="entry in languages"
            :key="entry.title"
            @click.prevent.stop="$i18n.setLocale(entry.language)"
            >{{ entry.title }}</b-nav-item
          >
        </b-navbar-nav>
        <b-navbar-nav class="ml-auto">
          <b-nav-item @click="handlePracharClick"
            >Prachar Prasar Resources</b-nav-item
          >
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
    <div v-if="homePage">
      <Hero />
      <PracharInformation />
      <Invitation />
    </div>
    <div v-else>
      <Resources @redirectHome="handlePracharClick" />
    </div>
  </div>
</template>

<script>
import i18n from "../nuxt.config";
export default {
  name: "IndexPage",
  i18n: {
    inject: true,
  },
  data() {
    return {
      languages: [
        { flag: "us", language: "en", title: "English" },
        { flag: "es", language: "mr", title: "Marathi" },
        { flag: "es", language: "hi", title: "Hindi" },
      ],
      homePage: true,
    };
  },
  methods: {
    handlePracharClick() {
      this.homePage = !this.homePage;
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Alegreya+Sans:ital,wght@0,400;0,500;0,700;0,800;0,900;1,400;1,500;1,700;1,800;1,900&display=swap");
.bg-info {
  background-color: #ba3b46 !important;
}
.navbar-dark .navbar-nav .nav-link {
  color: #ffeedb;
  font-size: 1.5rem;
}
.parent-container {
  font-family: "Alegreya Sans", sans-serif;
}
</style>
