<script setup>
import Header from "../Header/Header.vue";
import Textfield from "../Textfield/Textfield.vue";
import DisplayResult from "../DisplayResult/DisplayResult.vue";
import Numpad from "../Numpad/Numpad.vue";
</script>
<script>
const data = { clickedButton: null, textFieldState: "" };

export default {
  data() {
    return data;
  },
  methods: {
    handleClick(event) {
      if (event.target.classList.contains("button")) {
        const targetValue = event.target.textContent.split(" ");
        this.clickedButton = targetValue[0];
      }
    },
    defineButtonOperation() {
      const value = Number(this.clickedButton);
      if (this.clickedButton === "AC") {
        this.textFieldState = "";
      } else if (!isNaN(value)) {
        this.textFieldState = this.textFieldState + this.clickedButton;
      }
    },
  },
  watch: {
    clickedButton: "defineButtonOperation",
  },
};
</script>

<template>
  <div class="container">
    <Header></Header>
    <Textfield :textFieldValue="textFieldState"></Textfield>
    <DisplayResult></DisplayResult>
    <Numpad @click="handleClick"></Numpad>
  </div>
</template>

<style scoped>
.container {
  max-width: 420px;
  height: 100%;
  margin: 0 auto;
  background: #fbfbfb;
  padding: 24px;
  box-sizing: border-box;
  display: flex;
  flex-flow: column nowrap;
}
</style>
