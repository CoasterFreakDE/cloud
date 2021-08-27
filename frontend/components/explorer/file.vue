<template>
  <div class="file">
    <img
      v-if="type == 'folder'"
      class="file img"
      src="~/assets/icons/folder.svg"
    />
    <img v-else class="file img" src="~/assets/icons/file.svg" />
    <p class="text filename">{{ name }}</p>
    <p class="text">Last edited</p>
    <p class="text">Size</p>
    <p class="text">Last edited by</p>
  </div>
</template>

<script>
export default {
  props: ["name", "type", "shared"],
};
</script>

<style lang="scss" scoped>
.file {
  position: relative;
  -webkit-user-drag: none;
  user-select: none;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
  // cursor
  cursor: pointer;
  margin: 10px;
  background-color: rgba(240, 233, 233, 0.582);
  // width & height
  width: 600px;
  height: 80px;
  // flexen
  display: flex;
  flex-direction: row;
  & .img {
    height: 50px;
    width: 50px;
    position: relative;
    top: 6%;
  }
}
.text {
  position: relative;
  vertical-align: middle;
  top: 30%;
  margin-left: 10px;
}
</style>