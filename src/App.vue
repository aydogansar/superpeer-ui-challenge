<template>
  <div id="app">
    <CustomText>Benim</CustomText>
  </div>
</template>

<script>
import CustomText from "./components/CustomText";

export default {
  name: "App",
  components: {
    CustomText
  }
};
</script>

<style>
#app {
  width: 384px;
  height: 795px;
  color: var(--text-color);
  margin: 20px auto;
  background: var(--white);
  border-radius: 16px;
  padding: 32px 24px;
  box-shadow: var(--shadow);
  font-family: var(--font-body);
  font-size: var(--font-size);
  line-height: var(--line-height);
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
