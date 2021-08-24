<template>
  <div class="backgrounds">
    <button
      v-for="image in images"
      :key="image.pathShort"
      class="background"
      :style="{
        backgroundImage: `url(${image.pathLong})`,
      }"
      @click="setBg"
    ></button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [],
    };
  },
  methods: {
    importAll(r) {
      r.keys().forEach((key) =>
        this.images.push({ pathLong: r(key), pathShort: key })
      );
    },
    setBg(event) {
      let button = event.target;
      let bg = button.style.backgroundImage.slice(5, -2);
      this.$emit("bg-change", bg);
    },
  },
  beforeMount() {
    this.importAll(
      require.context("../../assets/images/", true, /^.*\.(jpg|png)$/)
    );
  },
};
</script>

<style lang="scss" scoped>
.backgrounds {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.background {
  width: 190px;
  height: 97px;
  margin: 8px;
  background-size: cover;
  background-position: center center;
  text-align: center;
  border-radius: 15px;
  // border: 2px solid blue;
  overflow: hidden;
  &:hover {
    border: 3px solid cadetblue;
  }
}
</style>