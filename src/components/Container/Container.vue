<script setup>
import Header from "../Header/Header.vue";
import Textfield from "../Textfield/Textfield.vue";
import DisplayResult from "../DisplayResult/DisplayResult.vue";
import Numpad from "../Numpad/Numpad.vue";
</script>
<script>
const data = {
  clickedButton: null,
  textFieldState: "",
  result: 0,
  currentTheme: "light",
};

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
      } else if (this.clickedButton === "=" && this.textFieldState.length > 0) {
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
    toggleTheme(event) {
      const target = event.target;
      if (
        target.classList.contains("header__wrapper") ||
        target.classList.contains("header__button")
      ) {
        const currentTheme = document.documentElement.dataset.theme;
        if (currentTheme === "light") {
          document.documentElement.dataset.theme = "dark";
          this.currentTheme = "dark";
        } else {
          document.documentElement.dataset.theme = "light";
          this.currentTheme = "light";
        }
      }
    },
  },
};
</script>

<template>
  <div class="container">
    <Header @click="toggleTheme" :theme="currentTheme" />
    <Textfield :textFieldValue="textFieldState" />
    <DisplayResult :result="result" />
    <Numpad @click="handleClick" :theme="currentTheme" />
  </div>
</template>

<style scoped>
.container {
  width: 100%;
  max-width: 420px;
  height: 100vh;
  max-height: 100vh;
  margin: 0 auto;
  padding: 24px;
  box-sizing: border-box;
  display: flex;
  flex-flow: column nowrap;
  transition: all 0.3s;
}

html[data-theme="dark"] .container {
  background: #1f1f1f;
}

html[data-theme="light"] .container {
  background: #fbfbfb;
}

@media (max-width: 375px) {
  .container {
    padding: 12px;
    max-height: 100dvh;
    height: 100dvh;
  }
}
</style>
