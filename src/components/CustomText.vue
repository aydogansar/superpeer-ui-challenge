<template>
  <component :is="tag" :class="classes">
    <slot />
  </component>
</template>

<script>
export default {
  name: "CustomText",
  data: function() {
    return {
      classes: `${this.color ? `text-${this.color}` : ""} ${this.size} ${
        this.muted ? "muted" : ""
      }`
    };
  },
  props: {
    tag: {
      type: String,
      default: "span"
    },
    color: {
      type: String
    },
    size: {
      type: String,
      default: ""
    },
    muted: {
      type: Boolean,
      default: false
    }
  }
};
</script>

<style scoped>
h3 {
  font-size: 24px;
  line-height: 29px;
  margin: 0 0 0 0;
}
</style>
