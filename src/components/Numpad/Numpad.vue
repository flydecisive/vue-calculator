<script setup>
import Button from "../Button/Button.vue";
</script>

<template>
  <div class="numpad">
    <Button
      :value="'AC'"
      :columnSpan="2"
      :backgroundColor="'#E6E6E6'"
      :rounded="'54px'"
      :color="'#1F1F1F'"
      :width="'100%'"
    />
    <Button :value="'x'" :backgroundColor="'#E6E6E6'" :color="'#1F1F1F'" />
    <Button :value="'÷'" :backgroundColor="'#FF9F0A'" />
    <Button :value="'7'" />
    <Button :value="'8'" />
    <Button :value="'9'" />
    <Button :value="'×'" :backgroundColor="'#FF9F0A'" />
    <Button :value="'4'" />
    <Button :value="'5'" />
    <Button :value="'6'" />
    <Button :value="'-'" :backgroundColor="'#FF9F0A'" />
    <Button :value="'1'" />
    <Button :value="'2'" />
    <Button :value="'3'" />
    <Button :value="'+'" :backgroundColor="'#FF9F0A'" />
    <Button :value="'0'" :columnSpan="3" :width="'100%'" :rounded="'54px'" />
    <Button :value="'='" :backgroundColor="'#FF9F0A'" />
  </div>
</template>

<style scoped lang="scss">
.numpad {
  width: 100%;
  min-height: 420px;
  height: 100%;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 13px;
  margin-top: 22px;
}
</style>
