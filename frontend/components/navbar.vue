<template>
  <header>
    <nuxt-link to="/"><home-icon class="icon" size="1.5x" v-tooltip.right="'Home'"/></nuxt-link>
    <nuxt-link to="/files"><folder-icon class="icon" size="1.5x" v-tooltip.right="'Files'"/></nuxt-link>
    <message-square-icon class="icon" size="1.5x" v-tooltip.right="'Chat'"/>
    <activity-icon class="icon" size="1.5x" v-tooltip.right="'Activity'"/>
  </header>
</template>

<script>
import { HomeIcon, FolderIcon, MessageSquareIcon, ActivityIcon } from "vue-feather-icons";
export default {
  components: { HomeIcon, FolderIcon, MessageSquareIcon, ActivityIcon },
};
</script>

<style lang="scss" scoped>

header {
  position: absolute;
  background-color: rgba(240, 233, 233, 0.582);
  width: 50px;
  height: 200px;
  z-index: 10000000;
  top: 50%;
  left: 2.5%;
  transform: translate(-50%, -50%);
  border-radius: 15px;
  display: flex;
  flex-direction: column;
}
.icon {
  z-index: inherit;
  position: relative;
  left: 50%;
  margin-top: 25px;
  transform: translate(-50%, -50%);
  stroke: rgba(70, 70, 70, 0.733);
  cursor:pointer;
    &:hover {
        stroke: rgba(70, 70, 70, 0.9);
    }
}

.icon-active {
    stroke: #fff;
}
</style>