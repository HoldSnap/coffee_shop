<script setup>
import { ref, computed } from "vue";
import categoriesData from "../stores/mock/Items.json";
import { selectedCategoryName } from "../stores/store.js";

const categories = ref(categoriesData.categories[0].categories);

const categoryNames = computed(() => ["All", ...categories.value.map(category => category.name)]);

const filteredItems = computed(() => {
  if (selectedCategoryName.value === "All" || selectedCategoryName.value === "") {
    return categoryNames.value.slice(1);
  }
  const selectedCategory = categories.value.find(category => category.name === selectedCategoryName.value);
  return selectedCategory ? selectedCategory.products : [];
});
</script>

<template>
  <section class="main_content content">
    <ul class="content__list">
      <li v-for="(item, index) in filteredItems" :key="index" class="content__item">
        <div v-if="selectedCategoryName === 'All'">
          {{ item }}
        </div>
        <div v-else>
          <img class="content__item_img" :src="item.img || 'default_image_path.jpg'" :alt="item.name" />
          <div class="content__item_name">{{ item.name }}</div>
          <div class="content__item_description">{{ item.description }}</div>
          <div v-if="item.price" class="content__item_price">${{ item.price }}</div>
        </div>
      </li>
    </ul>
  </section>
</template>


<style scoped></style>
