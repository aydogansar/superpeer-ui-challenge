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
      classes: `${this.color} ${this.size} ${this.muted ? "muted" : ""}`
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
    size: {
      type: String,
      default: "medium"
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
  font-size: var(--sm-font-size);
  line-height: var(--sm-line-height);
}
.primary {
  color: var(--primary-color);
}
h3 {
  font-size: 24px;
  line-height: 29px;
  margin: 0 0 0 0;
}
</style>
