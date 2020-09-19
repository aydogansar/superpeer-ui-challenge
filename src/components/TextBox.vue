<template>
  <span class="textbox">
    <component :is="component" v-if="icon" />
    <input type="text" @input="handleInput" />
  </span>
</template>
<script>
import { UserIcon } from "../icons";
import { icons } from "../icons";

export default {
  name: "TextBox",
  components: {
    UserIcon
  },
  props: {
    icon: {
      type: String
    }
  },
  data: function() {
    return {
      component: icons[this.icon]
    };
  },
  methods: {
    handleInput(e) {
      this.$emit("input", e.target.value);
    }
  }
};
</script>
<style scoped>
.textbox {
  width: 100%;
  border: var(--border);
  border-radius: var(--border-radius);
  padding: 12px;
  display: flex;
  align-items: center;
  justify-content: stretch;
}
svg {
  color: var(--primary-color);
  margin-right: 10px;
}
.textbox input[type="text"] {
  border: 0;
  width: 100%;
  outline: 0;
}
</style>
