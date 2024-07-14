<template>
  <section class="main_content content">
    <ul class="content__list">
      <li v-for="(item, index) in filteredItems" :key="index" class="content__item">
        <div class="content__item_img" v-html="item.img"></div>
        <div class="content__item_name">{{ item.name }}</div>
        <div class="content__item_description">{{ item.description }}</div>
        <div v-if="item.price" class="content__item_price">${{ item.price }}</div>
      </li>
    </ul>
  </section>
</template>

<script setup>
import {ref, computed} from "vue";
import categoriesData from "../stores/mock/Items.json";
import {selectedCategoryName} from "../stores/store.js";

const categories = ref(categoriesData.categories[0].categories);


const filteredItems = computed(() => {
  if (selectedCategoryName.value === "All" || selectedCategoryName.value === "") {
    return categories.value.map(category => ({
      img: category.img,
      name: "",
      description: "",
      price: null
    }));
  }
  const selectedCategory = categories.value.find(category => category.name === selectedCategoryName.value);
  return selectedCategory ? selectedCategory.products : [];
});
</script>
<style lang="scss" scoped>
@import "src/styles/utils/variables";
@import "src/styles/utils/mixins";

.main_content {
  margin-top: $primary-margin;
}



.content__list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 15px;

}
.content__item_img{
  @include svg-style(90px, $background-color);
}
.content__item{
  @include block-style(150px, 150px, $secondary-color, $border-radius-large)

}

</style>