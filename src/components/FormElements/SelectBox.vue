<template>
  <div class="selectbox" role="listbox">
    <select :name="name" @change="handleChange" class="border">
      <option v-for="option in options" :key="option">
        {{ option }}
      </option>
    </select>
    <ArrowIcon class="dropdown-icon" />
  </div>
</template>
<script>
import { ArrowIcon } from "../../icons";

export default {
  name: "SelectBox",
  components: {
    ArrowIcon
  },
  props: {
    name: {
      type: String
    },
    options: {
      type: Array
    }
  },
  methods: {
    handleChange(e) {
      this.$emit("input", e.target.value);
    }
  }
};
</script>
<style scoped>
.selectbox {
  position: relative;
  width: 100%;
}
select {
  padding: 15px;
  padding-right: 30px;
  width: 100%;
}
.dropdown-icon {
  position: absolute;
  right: 8px;
  top: 15px;
  pointer-events: none;
}
</style>
