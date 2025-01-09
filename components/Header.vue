<script>
import { headerDataLinks } from "~/assets/data/header.data";
export default {
  data() {
    return {
      links: headerDataLinks,
    };
  },
  methods: {},
  components: {},
};
</script>
<template>
  <header class="container header">
    <div class="header__logo">
      <img src="/STIK_LOGO.png" alt="" />
    </div>

    <nav class="header__menu">
      <ul class="menu">
        <li class="menu__item" v-for="link in links">
          <a class="menu__link" href="#">
            <img class="menu__img" :src="link.src" :alt="link.title" />
          </a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style>
.header {
  display: flex;
  align-items: center;
  position: relative;
  justify-content: end;
}

.header__logo {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
}

.header__menu {
  margin-block: 33px;
}

.menu {
  display: flex;
  align-items: center;
  gap: 16px;
}

.menu__item {
  list-style: none;
}

.menu__link {
  text-decoration: none;
  color: black;
}

.menu__img {
  transition: scale 0.3s ease-in;

  &:hover {
    scale: 1.2;
  }
}

@media screen and (max-width: 1000px) {
  .header {
    justify-content: center;
  }
}
</style>
