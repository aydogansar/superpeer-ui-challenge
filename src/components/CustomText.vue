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
      classes: `${this.color} ${this.muted ? "muted" : ""}`
    };
  },
  props: {
    tag: {
      type: String,
      default: "span"
    },
    color: {
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
.muted {
  color: var(--grey-80);
  font-size: 13px;
  line-height: 16px;
}
.primary {
  color: var(--primary-color);
}
</style>
