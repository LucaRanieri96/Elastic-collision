<script>
import SquareA from "./components/SquareA.vue";
import SquareB from "./components/SquareB.vue";

export default {
  components: {
    SquareA,
    SquareB,
  },
  methods: {
    startSimulation() {
      this.$refs.squareA.speed = 144;
      this.$refs.squareB.speed = -144;
    },
    resetSimulation() {
      this.$refs.squareA.speed = 0;
      this.$refs.squareB.speed = 0;
      this.$refs.squareA.positionX = 200;
      this.$refs.squareB.positionX = 700;
    },
  },
};
</script>

<template>
  <section class="vue-home">
    <div class="container" id="my_container">
      <SquareA ref="squareA"/>
      <SquareB ref="squareB"/>
    </div>
    <div class="container">
      <div class="row align-items-center flex-column">
        <button @click="startSimulation" class="btn btn-primary w-25 mt-4">Start simulation</button>
        <button @click="resetSimulation" class="btn btn-warning w-25 my-4">Reset simulation</button>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
@use "./styles/general.scss";

.vue-home {
  padding: 10rem;
  height: 100vh;
  color: #bbbbbb;
  background: #181818;
  font-family: Inter, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Fira Sans", "Droid Sans", "Helvetica Neue",
    sans-serif;
  font-size: 15px;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#my_container{
  position: relative;
  height: 800px;
  border: 1px solid;
}
</style>
