<template>
  <span class="textbox border" role="textbox" tabindex="0" @focus="handleFocus">
    <component :is="component" v-if="icon" />
    <input type="text" ref="textbox" @input="handleInput" />
  </span>
</template>
<script>
import { UserIcon } from "../../icons";
import { icons } from "../../icons";

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
    },
    handleFocus() {
      this.$refs.textbox.focus();
    }
  }
};
</script>
<style scoped>
.textbox {
  width: 100%;
  padding: 12px;
  display: flex;
  align-items: center;
  justify-content: stretch;
}
.textbox:focus-within {
  box-shadow: var(--focus-shadow);
}
svg {
  color: var(--primary-color);
  margin-right: 10px;
}
.textbox input[type="text"] {
  border: 0;
  width: 100%;
}
.textbox input[type="text"]:focus {
  box-shadow: none;
}
</style>
