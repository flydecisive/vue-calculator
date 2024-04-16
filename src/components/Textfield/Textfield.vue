<script>
export default {
  props: {
    textFieldValue: {
      type: String,
    },
  },
  computed: {
    style() {
      return {
        "font-size": this.textFieldValue.length > 40 ? "16px" : "32px",
        "line-height": this.textFieldValue.length > 40 ? "16px" : "32px",
      };
    },
  },
};
</script>

<template>
  <textarea
    class="textarea"
    :value="textFieldValue"
    :style="style"
    disabled
  ></textarea>
</template>

<style scoped lang="scss">
.textarea {
  width: 100%;
  height: 100%;
  min-height: 32px;
  border: none;
  resize: none;
  background: transparent;
  font-weight: 400;

  &:focus {
    border: none;
    outline: none;
  }
}

html[data-theme="dark"] .textarea {
  color: #ffffff;
}

html[data-theme="light"] .textarea {
  color: #1f1f1f;
}
</style>
