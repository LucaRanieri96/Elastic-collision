<script>
export default {
  name: "SquareA",
  data() {
    return {
      speed: 3,
      positionX: 200,
      containerWidth: 1320,
      squareWidth: 150,
    };
  },
  mounted() {
    this.positionX = 200;
    const frameRate = 144;
    const interval = 1000 / frameRate;

    setInterval(() => {
      this.positionX += this.speed * (interval / 1000);

      if (this.positionX <= 0 || this.positionX + this.squareWidth >= this.containerWidth) {
        this.speed *= -1;
      }

    }, interval);
  },
};
</script>

<template>
  <div id="squareA" :style="{ left: positionX + 'px' }"></div>
</template>

<style lang="scss" scoped>
#squareA {
  position: absolute;
  bottom: 0;
  height: 150px;
  width: 150px;
  border: 1px solid black;
  background-color: rgb(5, 251, 5);
}
</style>
