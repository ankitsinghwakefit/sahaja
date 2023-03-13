<template>
  <b-container fluid>
    <b-row>
      <b-col>
        <div class="hero-content">
          <h2>{{ $t("resourceHeading") }}</h2>
          <h4>{{ $t("resourcePara") }}</h4>
          <a href="https://library.sahajaworld.org/resources" target="_blank"
            >Get Prachar Prasar Resource</a
          >
          <button @click="handleHomeClick" class="mt-4">Home</button>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import i18n from "../nuxt.config";

export default {
  name: "Resources",
  i18n: {
    inject: true,
  },
  methods: {
    handleHomeClick() {
      this.$emit("redirectHome");
    },
  },
};
</script>

<style scoped>
.container-fluid {
  background-color: #ba3b46;
  color: #ffeedb;
  border-bottom: 2px solid #ffeedb;
}
.img-fluid {
  object-fit: cover;
  object-fit: fill;
}
h1 {
  /* color: orangered; */
  font-weight: 800;
  font-style: italic;
}
.hero-content {
  display: flex;
  justify-content: center;
  align-items: center;
  align-content: center;
  flex-direction: column;
  padding: 5%;
}
a,
button {
  background-color: #ffeedb;
  border: none;
  color: #ba3b46;
  padding: 8px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin-right: 5px;
  border-radius: 4px;
  font-weight: 600;
}
</style>
