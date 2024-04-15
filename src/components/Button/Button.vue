<script>
export default {
  props: {
    value: String,
    columnSpan: {
      type: Number,
      required: false,
      default: 1,
    },
    backgroundColor: {
      type: String,
      default: "#626262",
    },
    color: {
      type: String,
      default: "#FBFBFB",
    },
    rounded: {
      type: String,
      default: "50%",
    },
    width: {
      type: String,
      default: "72px",
    },
  },
  computed: {
    style() {
      return {
        background: this.backgroundColor,
        "grid-column": `span ${this.columnSpan}`,
        color: this.color,
        "border-radius": this.rounded,
        width: this.width,
      };
    },
  },
};
</script>

<template>
  <div class="button" :style="style">
    {{ value }} <span class="square" v-if="value === 'x'">2</span>
  </div>
</template>

<style lang="scss" scoped>
.button {
  width: 100%;
  height: 72px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 36px;
  line-height: 36px;
  font-weight: 400;
  position: relative;
  transition: all 0.3s;

  &:hover {
    cursor: pointer;
  }

  &:active {
    opacity: 0.5;
  }
}

.square {
  font-size: 18px;
  line-height: 18px;
  position: absolute;
  top: 15px;
  right: 15px;
}
</style>
