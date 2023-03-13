<template>
  <b-container fluid>
    <b-row>
      <b-col lg="8" md="8" sm="12">
        <div class="instruction-content">
          <h5>{{ $t("instructionOne") }}</h5>
          <h5>{{ $t("instructionTwo") }}</h5>
          <h5>{{ $t("instructionThree") }}</h5>
          <h5>{{ $t("instructionFour") }}</h5>
          <h5>{{ $t("instructionFive") }}</h5>
        </div>
      </b-col>
      <b-col lg="4" md="4" sm="12" class="count">
        <div class="hero-content">
          <h1 class="mb-2">{{ finalCount }}</h1>
          <button class="mb-4" @click="handleCountUp">
            {{ $t("coming") }}
          </button>
          <h4>{{ $t("upvote") }}</h4>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "Invitation",
  data() {
    return {
      count: 0,
      finalCount: 0,
    };
  },
  mounted() {
    this.setCount();
  },
  methods: {
    async setCount() {
      let resp = await this.$axios.$get(
        "https://rose-important-hedgehog.cyclic.app/api/count"
      );
      this.count = resp.people;
      this.finalCount = resp.people;
    },
    handleCountUp() {
      this.finalCount += 1;
      let countUpBy = this.finalCount - this.count;
      this.$axios.$post(
        "https://rose-important-hedgehog.cyclic.app/api/count",
        {
          people: countUpBy,
        }
      );
    },
  },
};
</script>

<style scoped>
.container-fluid {
  background-color: #ba3b46;
  color: #ffeedb;
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
.instruction-content {
  padding: 20px;
}
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
/* .count {
    background-color: #58ff66;
    color: white;
} */
</style>
