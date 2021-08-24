<template>
  <div class="ct">
    <div
      class="thumbnail"
      :style="{backgroundImage: `url(${img})`}
      "
    />
    <div class="details">
      <span>{{file}}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["file", "img"]
};
</script>

<style lang="scss" scoped>
.ct {
  width: auto;
  height: 60px;
  margin-bottom: 5px;
  &:hover {
    background-color: rgba(228, 224, 224, 0.884);
    cursor: pointer;
    border-radius: 5px;
  }
  & .details {
    position: relative;
    top: 50%;
    left: 30%;
    transform: translate(-50%, -50%);
    & span {
      color: rgb(70, 70, 70);
    }
  }
  .thumbnail {
    border-radius: 5px;
    margin-left: 15px;
    position: relative;
    top: 50%;
    left: 10%;
    transform: translate(-50%, -50%);
    width: 44px;
    height: 44px;
    text-align: right;
    float: left;
    background-repeat: no-repeat;
    background-size: cover;
  }
}
</style>