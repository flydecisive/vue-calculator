<script>
export default {
  props: {
    result: {
      type: Number,
    },
  },
  computed: {
    style() {
      return {
        "font-size": this.result > 12 ? "24px" : "48px",
      };
    },
  },
};
</script>

<template>
  <p class="result" :style="style">{{ result }}</p>
</template>

<style scoped lang="scss">
.result {
  font-weight: 400;
  line-height: 58px;
  width: 100%;
  text-align: right;
}

html[data-theme="dark"] .result {
  color: #ffffff;
}

html[data-theme="light"] .result {
  color: #1f1f1f;
}
</style>
