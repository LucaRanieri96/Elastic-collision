<script>
export default {
  name: "SquareB",
  data() {
    return {
      speed: 3,
      positionX: 700,
      containerWidth: 1320,
      squareWidth: 150
    };
  },
  mounted() {
    this.positionX = 700;
    const frameRate = 144;
    const interval = 1000 / frameRate;

    setInterval(() => {
      this.positionX += this.speed * (interval / 1000);

      if (this.positionX + this.squareWidth >= this.containerWidth || this.positionX <=0 ) {
        this.speed *= -1;
      }

    }, interval);
  },
};
</script>

<template>
  <div id="squareB" :style="{ left: positionX + 'px' }"></div>
</template>

<style scoped>
#squareB {
  position: absolute;
  bottom: 0;
  height: 150px;
  width: 150px;
  border: 1px solid black;
  background-color: rgb(251, 157, 5);
}
</style>
