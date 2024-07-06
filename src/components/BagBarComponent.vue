<script setup></script>

<template>
  <aside class="main__bag bag">
    <div class="bag__info">
      <div class="bag__info_number"></div>
      <div class="input">
        <input class="input__number" />
        <input class="input__name" />
      </div>
    </div>
    <ul class="bag__list">
      <li class="bag__item"></li>
      <li class="bag__item"></li>
      <li class="bag__item"></li>
      <li class="bag__item"></li>
    </ul>
    <div class="bag__total">
      <div class="bag__total_quantity"></div>
      <div class="bag__total_prise"></div>
    </div>
    <div class="bag__buy">
      <button class="bag__buy_button">Buy</button>
    </div>
  </aside>
</template>

<style lang="scss" scoped>
@import "src/styles/utils/variables";

.main__bag {
  margin-right: $primary-margin;
}

.bag {
  margin: $primary-margin;
  background-color: white;
  border-radius: $border-radius-medium;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);

  &__info {
  }
}
</style>
