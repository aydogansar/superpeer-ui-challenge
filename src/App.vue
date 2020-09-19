<template>
  <div id="app">
    <CustomText color="primary" size="small">Call with</CustomText>
    <CustomText tag="h3">Niloya Kayıkçı</CustomText>
    <DateDisplay />
  </div>
</template>

<script>
import CustomText from "./components/CustomText";
import DateDisplay from "./components/DateDisplay";

export default {
  name: "App",
  components: {
    CustomText,
    DateDisplay
  },
  data: function() {
    return {
      text: ""
    };
  }
};
</script>

<style>
#app {
  max-width: 384px;
  color: var(--text-color);
  margin: 20px auto;
  background: var(--bg-color);
  border-radius: 16px;
  padding: 32px 24px;
  box-shadow: var(--shadow);
  font-family: var(--font-family-body);
  font-size: var(--font-size);
  line-height: var(--line-height);
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
