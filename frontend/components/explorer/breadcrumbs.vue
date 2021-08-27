<template>
  <div style="display: flex; flex-direction: row">
    <div class="crumbs" v-for="crumb in crumbs" :key="crumb.name">
        <a :href="crumb.url">{{crumb.name}}</a> <span class="m-x-10">/</span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["crumbs"],
};
</script>

<style lang="scss" scoped>
.m-x-10 {
  margin-right: 10px;
  margin-left: 10px;
}
</style>