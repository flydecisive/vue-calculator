<script>
export default {
  props: {
    textFieldValue: {
      type: String,
    },
  },
};
</script>

<template>
  <textarea class="textarea" :value="textFieldValue"></textarea>
</template>

<style scoped lang="scss">
.textarea {
  width: 100%;
  height: 100%;
  min-height: 32px;
  border: none;
  resize: none;
  background: transparent;
  font-size: 32px;
  line-height: 32px;
  font-weight: 400;
  color: #1f1f1f;

  &:focus {
    border: none;
    outline: none;
  }
}
</style>
