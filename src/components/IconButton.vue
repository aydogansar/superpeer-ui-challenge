<template>
  <button class="btn-icon" :class="colorClass">
    <component :is="component"></component>
  </button>
</template>

<script>
import MicIcon from "../icons/microphone.svg";
import CameraIcon from "../icons/camera.svg";
import OptionsIcon from "../icons/options.svg";

const icons = {
  mic: "MicIcon",
  camera: "CameraIcon",
  options: "OptionsIcon"
};
export default {
  name: "IconButton",
  components: {
    MicIcon,
    CameraIcon,
    OptionsIcon
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
      default: ""
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
