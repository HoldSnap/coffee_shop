<script setup></script>

<template>
  <aside class="main__sidebar sidebar">
    <ul class="sidebar__list">
      <li class="sidebar__item">
        <img
          src="/src/assets/logo/logo-no-background.png"
          alt="logo"
          class="sidebar__logo"
        />
      </li>
      <li class="sidebar__item">
        <a href="#" class="sidebar__link">Menu</a>
      </li>
      <li class="sidebar__item">
        <a href="#" class="sidebar__link">Orders</a>
      </li>
    </ul>
  </aside>
</template>

<style lang="scss" scoped>
@import "src/styles/utils/variables";

.main__sidebar {
  width: 20%;
}
.sidebar__item {
  width: 50%;
  margin: $primary-margin;
}
</style>
