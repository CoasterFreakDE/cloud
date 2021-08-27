<template>
  <div>
    <navbar />
    <Nuxt id="content"/>
  </div>
</template>

<script>
import navbar from "~/components/global/navbar.vue";
export default {
  components: { navbar },
};
</script>

<style>
#content {
    padding-top: 0 !important;
}

#content {
    box-sizing: border-box;
    position: relative;
    display: flex;
    padding-top: 50px;
    min-height: 100%;
    font-family: "Roboto";
}
</style>