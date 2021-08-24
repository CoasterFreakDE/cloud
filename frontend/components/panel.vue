<template>
  <div class="panel">
    <div class="header">
      <h2 style="color: rgb(70, 70, 70);">{{title}}</h2>
    </div>
    <div class="content">
      <ul style="margin: 0 !important">
        <li
          class="container"
          v-for="file in data"
          :key="file.name"
          v-tooltip="file.path"
        >
          <filecard :file="file.name" :img="file.image"/>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
import Filecard from "./filecard.vue";
export default {
  components: { Filecard },
  props: ["title", "data"],
};
</script>
<style lang="scss" scoped>
.panel {
  width: 320px;
  max-width: 100%;
  background-color: rgba(240, 233, 233, 0.582);
  //opacity: 0.6;
  margin: 16px;
  border-radius: 15px;
  & .header {
    padding: 16px;
    user-select: none;
    text-align: center;
    margin: 5px;
    font-size: 20px;
    font-weight: 500;
    & h2 {
      &:hover {
        cursor: grab;
      }
    }
  }
  & .content {
    margin: 0 16px 16px 16px;
    height: 420px;
    & .thumbnail {
      margin-left: 8px;
      width: 44px;
      height: 44px;
      text-align: right;
      float: right;
    }
    & .filename {
      text-align: left;
    }
    & .container {
      overflow: hidden;
      text-align: center;
      vertical-align: middle;
      margin: 0 auto;
      & .thumbnail {
        float: left;
        width: 44px;
        height: 44px;
        border-radius: 5px;
      }
      & .details {
        float: left;
        margin-left: 20px;
        margin-top: 7px;
      }
    }
  }
}
</style>