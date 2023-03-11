<template>
<b-container fluid>
  <b-row>
    <b-col lg="6" md="6" sm="12"><b-img src="../images/mother3.jpg" fluid alt="Responsive image"></b-img></b-col>
    <b-col lg="6" md="6" sm="12">
        <div class="hero-content">
          <div class="transaltion-box"><button v-for="entry in languages" :key="entry.title" @click.prevent.stop="$i18n.setLocale(entry.language)">{{entry.title}}</button></div>
         <h1>{{ $t('grace') }}</h1>
        <h1>{{ $t('know') }}</h1>
        <h1>{{ $t('can') }}</h1>
        <h1>{{ $t('will') }}</h1>
        <h1>{{ $t('call') }}</h1>
        </div>
    </b-col>
  </b-row>
</b-container>
  <!-- <div>
  <b-nav-item href="#">{{ $t('home') }}</b-nav-item>
</div> -->
</template>

<script>
import i18n from "../nuxt.config";

export default {
    name: "Hero",
      i18n: {
      inject: true
    },
  data() {
    return {
        languages: [
            { flag: 'us', language: 'en', title: 'English' },
            { flag: 'es', language: 'mr', title: 'Marathi' },
            { flag: 'es', language: 'hi', title: 'Hindi' }
        ]
    };
}
}
</script>

<style scoped>
/* .container {
    max-width: 100% !important;
} */
.img-fluid {
    object-fit: cover;
    object-fit: fill;
}
h1 {
    color: #BA3B46;
    font-size: 2.1rem;
    font-weight: 800;
    font-style: italic;
    word-spacing: 7px;
}
.hero-content {
    display: flex;
    justify-content: center;
    align-items: center;
    align-content: center;
    flex-direction: column;
    /* padding-top: 2rem; */
}
.transaltion-box {
    padding: 20px;
  } 
  button {
      background-color: #BA3B46;
    border: none;
    color: #FFEEDB;
    padding: 8px 20px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin-right: 5px;
    border-radius: 4px;
    font-weight: 600;
}
@media screen and (min-width: 786px) {
  .transaltion-box {
    display: none;
  }
  .hero-content {
    padding-top: 2.5rem;
}
}
</style>