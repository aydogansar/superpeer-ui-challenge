<template>
  <button class="btn-icon" :class="colorClass">
    <component :is="component"></component>
  </button>
</template>

<script>
import {
  ArrowIcon,
  CalendarIcon,
  CameraIcon,
  ClockIcon,
  MicIcon,
  OptionsIcon,
  UserIcon
} from "../icons";
import { icons } from "../icons";

export default {
  name: "IconButton",
  components: {
    ArrowIcon,
    CalendarIcon,
    CameraIcon,
    ClockIcon,
    MicIcon,
    OptionsIcon,
    UserIcon
  },
  data: function() {
    return {
      component: icons[this.icon],
      colorClass: `text-${this.color}`
    };
  },
  props: {
    icon: {
      type: String,
      default: "mic"
    },
    color: {
      type: String,
      default: "color"
    }
  }
};
</script>

<style scoped>
.btn-icon {
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 999px;
  border: 0;
  background: var(--grey-10);
  padding: 15px;
}
</style>
