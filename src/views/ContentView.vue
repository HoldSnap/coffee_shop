<script setup>
import HeaderComponent from "../components/HeaderComponent.vue";
import SideBarComponent from "../components/SideBarComponent.vue";
import BagBarComponent from "../components/BagBarComponent.vue";
import ContentComponent from "../components/ContentComponent.vue";
</script>

<template>
  <div class="container">
    <SideBarComponent></SideBarComponent>
    <div class="container__content">
      <HeaderComponent></HeaderComponent>
      <ContentComponent></ContentComponent>
    </div>
    <BagBarComponent></BagBarComponent>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  height: 100vh;
}
.container__content {
  width: 60%;
}
</style>
