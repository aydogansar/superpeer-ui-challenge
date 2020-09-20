<template>
  <span class="form-input">
    <CustomText v-if="title">{{ title }}</CustomText>
    <component
      :is="input"
      :options="options"
      :icon="icon"
      :variant="variant"
      @input="handleInput"
      @change="handleInput"
      :class="{ input: title }"
      >{{ text }}</component
    >
  </span>
</template>
<script>
import CustomText from "./CustomText";
import { SelectBox, TextBox, Button } from "./FormElements";
import PlaySound from "./PlaySound";

export default {
  name: "FormInput",
  components: {
    CustomText,
    SelectBox,
    TextBox,
    Button,
    PlaySound
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
  },
  methods: {
    handleInput(value) {
      this.$emit("input", value);
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
.input {
  width: 235px;
}
</style>
