<script>
import ThemeIconLight from "../../assets/theme-icon.svg";
import ThemeIconDark from "../../assets/theme-icon-dark.svg";

export default {
  data() {
    return {
      ThemeIconLight,
      ThemeIconDark,
    };
  },
  props: {
    theme: String,
  },
};
</script>

<template>
  <header class="header">
    <div class="header__wrapper">
      <img
        :src="theme === 'light' ? ThemeIconLight : ThemeIconDark"
        alt="theme"
        class="header__button"
      />
    </div>
  </header>
</template>

<style scoped lang="scss">
.header {
  width: 100%;
  display: flex;
  justify-content: flex-end;
  margin-bottom: 8px;

  &__wrapper {
    width: 24px;
    height: 24px;
  }

  &__button {
    &:hover {
      cursor: pointer;
    }
  }
}
</style>
