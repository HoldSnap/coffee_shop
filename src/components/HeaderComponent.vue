<template>
  <header class="header">
    <div class="header__top">
      <div class="header__info">
        <div class="header__date">Sunday, June 20 2021</div>
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
        <li class="categories__item">
          <button class="categories__item_button">Categories</button>
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
@import "src/styles/utils/variables";

.header {
  font-family: $font-family-base;
  width: 100%;
  display: flex;
  flex-direction: column;
  margin-top: $primary-margin;
  padding-right: 25px;
}

.header__top {
  display: flex;
  width: 100%;
}

.header__info {
  display: flex;
  width: 100%;
  flex-direction: column;
}

.header__search {
  position: relative;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  width: 40vw;
  height: 50px;
}

.header__input {
  width: 100%;
  height: 100%;
  border: none;
  outline: none;
  padding-left: 3rem;
  border-radius: 8px;
  color: $primary-color;
}

.header__icon {
  position: absolute;
  left: 10px;
  top: 50%;
  transform: translateY(-50%);
  width: 30px;
  height: 30px;
  stroke: $primary-color;
}

.categories__list {
  display: flex;
}
</style>
