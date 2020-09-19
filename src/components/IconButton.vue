<template>
  <button>
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
      component: icons[this.icon]
    };
  },
  props: {
    icon: {
      type: String
    }
  }
};
</script>
