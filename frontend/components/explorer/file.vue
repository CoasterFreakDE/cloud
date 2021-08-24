<template>
  <div class="file">
    <img
      v-if="type == 'folder'"
      class="file img"
      src="~/assets/icons/folder.svg"
    />
    <img v-else class="file img" src="~/assets/icons/file.svg" />
    <p class="filename">{{ name }}</p>
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
  // background-color: rgba(240, 233, 233, 0.582);
  // width & height
  height: 60px;
  width: 60px;
  
  & p {
  }

  & .img {
    height: 50px;
    width: 50px;
  }
}
</style>