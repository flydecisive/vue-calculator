<script>
export default {
  props: {
    result: {
      type: Number,
    },
  },
};
</script>

<template>
  <p class="result">{{ result }}</p>
</template>

<style scoped lang="scss">
.result {
  font-weight: 400;
  font-size: 48px;
  line-height: 58px;
  color: #1f1f1f;
  width: 100%;
  text-align: right;
}
</style>
