<script setup>

</script>

<template>
  <header class="header">

    <div class="header__top">

      <div class="header__date">
        june 20 20
      </div>
      <div class="header__field">
        Categories
      </div>
      <div class="header__search">
        <input>
      </div>
    </div>
    <nav class="header__categories categories">
      <ul class="categories__list">
        <li class="categories__item">
          <a class="categories__item_button">Categories</a>
        </li>
        <li class="categories__item">
          <button class="categories__item_button">All</button>
        </li>
        <li class="categories__item">
          <button class="categories__item_button">Water</button>
        </li>
        <li class="categories__item">
          <button class="categories__item_button">Coffee</button>
        </li>
      </ul>
    </nav>
  </header>

</template>

<style lang="scss" scoped>
.header {
  width: 60%;
}
</style>