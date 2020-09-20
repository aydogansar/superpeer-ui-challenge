<template>
  <span class="form-input">
    <CustomText v-if="title" class="title">{{ title }}</CustomText>
    <component :is="input" :options="options" :icon="icon" :variant="variant">{{
      text
    }}</component>
  </span>
</template>
<script>
import CustomText from "./CustomText";
import { SelectBox, TextBox, Button } from "./Inputs";
export default {
  name: "FormInput",
  components: {
    CustomText,
    SelectBox,
    TextBox,
    Button
  },
  props: {
    title: {
      type: String
    },
    input: {
      type: String
    },
    options: {
      type: Array
    },
    icon: {
      type: String
    },
    text: {
      type: String
    },
    variant: {
      type: String
    }
  }
};
</script>
<style scoped>
.form-input {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}
.title {
  width: 145px;
}
</style>
