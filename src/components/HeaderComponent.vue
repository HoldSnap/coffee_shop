<script setup>
import { onMounted, ref, computed } from "vue";
import categoriesData from "../stores/mock/Items.json";
import { selectedCategoryName, activeCategoryIndex } from "../stores/store.js";

const currentDate = ref("");
const categories = ref(categoriesData.categories[0].categories);

const formatCurrentDate = () => {
  const options = {
    weekday: "long",
    month: "long",
    day: "numeric",
    year: "numeric",
  };
  currentDate.value = new Date().toLocaleDateString("en-US", options);
};

const allCategories = computed(() => {
  return ["All", ...categories.value.map(category => category.name)];
});

const setActive = (index) => {
  activeCategoryIndex.value = index;
  selectedCategoryName.value = index === 0 ? "" : categories.value[index - 1].name;
};

onMounted(() => {
  formatCurrentDate();
});
</script>

<template>
  <header class="header">
    <div class="header__top">
      <div class="header__info">
        <div class="header__date">{{ currentDate }}</div>
        <div class="header__field">Menu</div>
      </div>
      <div class="header__search">
        <input class="header__input" type="text" placeholder="Search..." />
        <svg
          class="header__icon"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <circle cx="11" cy="11" r="8"></circle>
          <line x1="21" y1="21" x2="16.65" y2="16.65"></line>
        </svg>
      </div>
    </div>
    <nav class="header__categories categories">
      <ul class="categories__list">
        <li
          class="categories__item"
          v-for="(category, index) in allCategories"
          :key="index"
        >
          <button
            class="categories__item_button"
            :class="{
              'categories__item_button--active': activeCategoryIndex === index,
            }"
            @click="setActive(index)"
          >
            {{ category }}
          </button>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style lang="scss" scoped>
@import "src/styles/utils/variables";

// Блок: header
.header {
  font-family: $font-family-base;
  width: 100%;
  display: flex;
  flex-direction: column;
  margin-top: $primary-margin;
  padding-right: 25px;

  &__top {
    display: flex;
    width: 100%;
  }

  &__info {
    display: flex;
    width: 100%;
    flex-direction: column;
  }

  &__search {
    position: relative;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    width: 40vw;
    height: 50px;
  }

  &__input {
    width: 100%;
    height: 100%;
    border: none;
    outline: none;
    padding-left: 3rem;
    border-radius: 8px;
    color: $primary-color;
  }

  &__icon {
    position: absolute;
    left: 10px;
    top: 50%;
    transform: translateY(-50%);
    width: 30px;
    height: 30px;
    stroke: $primary-color;
  }

  &__date {
    color: $unable-color;
  }

  &__field {
    margin-top: 10px;
    font-family: $font-family-base;
    font-size: $font-size-large;
    font-weight: $font-weight-bold;
  }

  &__categories {
    margin-top: $primary-margin;
  }
}

.categories {
  &__list {
    display: flex;
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
  }

  &__item {
    flex: 0 0 auto;

    &:not(:last-child) {
      margin-right: 12px;
    }
  }

  &__item_button {
    border: none;
    outline: none;
    background-color: $background-color;
    color: $button-color;
    margin-left: 10px;
  }

  &__item_button {
    border: none;
    outline: none;
    background-color: $background-color;
    color: $button-color;
    cursor: pointer;
    font-size: $font-size-base;

    &--active {
      color: $primary-color;
      font-weight: $font-weight-bold;
      border-bottom: 2px solid $primary-color;
    }
  }
}
</style>
