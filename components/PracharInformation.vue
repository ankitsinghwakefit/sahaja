<template>
  <b-container fluid>
    <b-row>
      <b-col>
        <div class="hero-content">
          <h1>{{ $t("date") }}</h1>
          <h2>{{ $t("slogan") }}</h2>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "PracharInformation",
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
</style>
