<template>
  <button class="btn border" :class="classes">
    <slot />
  </button>
</template>
<script>
export default {
  name: "Button",
  data: function() {
    return {
      classes: `${this.variant}`
    };
  },
  props: {
    variant: {
      type: String,
      default: "primary"
    }
  }
};
</script>
<style scoped>
.btn {
  border-radius: var(--border-radius);
  padding: 15px;
  width: 100%;
}
.primary {
  background: var(--primary-color);
  color: var(--white);
}
.outline-primary {
  color: var(--primary-color);
  background: var(--white);
  border-color: var(--primary-color);
}
</style>
