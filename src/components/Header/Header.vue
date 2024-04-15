<script>
import ThemeIcon from "../../assets/theme-icon.svg";

export default {
  data() {
    return {
      ThemeIcon,
    };
  },
};
</script>

<template>
  <header class="header">
    <img :src="ThemeIcon" alt="theme" class="header__button" />
  </header>
</template>

<style scoped lang="scss">
.header {
  width: 100%;
  display: flex;
  justify-content: flex-end;
  margin-bottom: 8px;

  &__button {
    &:hover {
      cursor: pointer;
    }
  }
}
</style>
