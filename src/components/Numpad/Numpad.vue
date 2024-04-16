<script setup>
import Button from "../Button/Button.vue";
</script>
<script>
export default {
  props: {
    theme: String,
  },
};
</script>

<template>
  <div class="numpad">
    <Button
      :value="'AC'"
      :columnSpan="2"
      :backgroundColor="theme === 'light' ? '#E6E6E6' : '#515151'"
      :rounded="'54px'"
      :color="theme === 'light' ? '#1F1F1F' : '#FFFFFF'"
      :width="'100%'"
    />
    <Button
      :value="'x'"
      :backgroundColor="theme === 'light' ? '#E6E6E6' : '#E6E6E6'"
      :color="'#1F1F1F'"
    />
    <Button
      :value="'÷'"
      :backgroundColor="'#FF9F0A'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
    />
    <Button
      :value="'7'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
      :backgroundColor="theme === 'light' ? '#626262' : '#E6E6E6'"
    />
    <Button
      :value="'8'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
      :backgroundColor="theme === 'light' ? '#626262' : '#E6E6E6'"
    />
    <Button
      :value="'9'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
      :backgroundColor="theme === 'light' ? '#626262' : '#E6E6E6'"
    />
    <Button
      :value="'×'"
      :backgroundColor="'#FF9F0A'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
    />
    <Button
      :value="'4'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
      :backgroundColor="theme === 'light' ? '#626262' : '#E6E6E6'"
    />
    <Button
      :value="'5'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
      :backgroundColor="theme === 'light' ? '#626262' : '#E6E6E6'"
    />
    <Button
      :value="'6'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
      :backgroundColor="theme === 'light' ? '#626262' : '#E6E6E6'"
    />
    <Button
      :value="'-'"
      :backgroundColor="'#FF9F0A'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
    />
    <Button
      :value="'1'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
      :backgroundColor="theme === 'light' ? '#626262' : '#E6E6E6'"
    />
    <Button
      :value="'2'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
      :backgroundColor="theme === 'light' ? '#626262' : '#E6E6E6'"
    />
    <Button
      :value="'3'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
      :backgroundColor="theme === 'light' ? '#626262' : '#E6E6E6'"
    />
    <Button
      :value="'+'"
      :backgroundColor="'#FF9F0A'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
    />
    <Button
      :value="'0'"
      :columnSpan="3"
      :width="'100%'"
      :rounded="'54px'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
      :backgroundColor="theme === 'light' ? '#626262' : '#E6E6E6'"
    />
    <Button
      :value="'='"
      :backgroundColor="'#FF9F0A'"
      :color="theme === 'light' ? '#FBFBFB' : '#1F1F1F'"
    />
  </div>
</template>

<style scoped lang="scss">
.numpad {
  width: 100%;
  min-height: 420px;
  height: 100%;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  justify-content: space-between;
  gap: 13px;
  margin-top: 22px;
}
</style>
