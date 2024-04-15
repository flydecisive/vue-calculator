<script setup>
import Header from "../Header/Header.vue";
import Textfield from "../Textfield/Textfield.vue";
import DisplayResult from "../DisplayResult/DisplayResult.vue";
import Numpad from "../Numpad/Numpad.vue";
</script>
<script>
const data = { clickedButton: null, textFieldState: "", result: 0 };

export default {
  data() {
    return data;
  },
  methods: {
    handleClick(event) {
      if (event.target.classList.contains("button")) {
        const targetValue = event.target.textContent.split(" ");
        this.clickedButton = targetValue[0];
        this.defineButtonOperation();
      }
    },
    defineButtonOperation() {
      if (this.clickedButton === "AC") {
        this.textFieldState = "";
        this.result = 0;
      } else if (!isNaN(Number(this.clickedButton))) {
        this.textFieldState = this.textFieldState + this.clickedButton;
      } else if (
        (this.clickedButton === "+" ||
          this.clickedButton === "÷" ||
          this.clickedButton === "×" ||
          this.clickedButton === "-") &&
        this.textFieldState.length > 0
      ) {
        this.textFieldState =
          this.textFieldState + " " + this.clickedButton + " ";
      } else if (this.clickedButton === "=") {
        this.countResult();
      } else if (this.clickedButton === "x" && this.textFieldState.length > 0) {
        this.result = Number(this.textFieldState) ** 2;
      }
    },
    countResult() {
      let values = this.textFieldState.split(" ");
      if (values.includes("×")) {
        let index = 0;
        while (values.includes("×")) {
          if (values[index] === "×") {
            let result = Number(values[index - 1]) * Number(values[index + 1]);
            values.splice(index - 1, 3, result);
            index = 0;
          } else {
            index += 1;
          }
        }
      }

      if (values.includes("÷")) {
        let index = 0;
        while (values.includes("÷")) {
          if (values[index] === "÷") {
            let result = Number(
              (Number(values[index - 1]) / Number(values[index + 1])).toFixed(3)
            );
            values.splice(index - 1, 3, result);
            index = 0;
          } else {
            index += 1;
          }
        }
      }

      if (values.includes("+")) {
        let index = 0;
        while (values.includes("+")) {
          if (values[index] === "+") {
            let result = Number(values[index - 1]) + Number(values[index + 1]);
            values.splice(index - 1, 3, result);
            index = 0;
          } else {
            index += 1;
          }
        }
      }

      if (values.includes("-")) {
        let index = 0;
        while (values.includes("-")) {
          if (values[index] === "-") {
            let result = Number(values[index - 1]) - Number(values[index + 1]);
            values.splice(index - 1, 3, result);
            index = 0;
          } else {
            index += 1;
          }
        }
      }

      if (values.length === 1) {
        this.result = values[0];
      }
    },
  },
};
</script>

<template>
  <div class="container">
    <Header></Header>
    <Textfield :textFieldValue="textFieldState"></Textfield>
    <DisplayResult :result="result"></DisplayResult>
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
