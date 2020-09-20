<template>
  <div class="video-call mt-5">
    <div class="controls">
      <IconButton
        icon="mic"
        class="shadow"
        :class="{ active: active.mic }"
        aria-label="Microphone on/off"
        @click.native="active.mic = !active.mic"
      />
      <IconButton
        icon="camera"
        class="shadow"
        :class="{ active: active.camera }"
        aria-label="Camera on/off"
        @click.native="active.camera = !active.camera"
      />
      <IconButton
        icon="options"
        class="shadow"
        :class="{ active: active.options }"
        aria-label="Options"
        @click.native="active.options = !active.options"
      />
    </div>
  </div>
</template>
<script>
import IconButton from "./IconButton";

export default {
  name: "VideoCall",
  components: {
    IconButton
  },
  data: function() {
    return {
      active: {
        mic: false,
        camera: false,
        options: false
      }
    };
  }
};
</script>
<style scoped>
.video-call {
  border-radius: var(--border-radius);
  background: url("/img/videocall.jpg") center no-repeat;
  background-size: 100%;
  width: 100%;
  height: 190px;
  position: relative;
}
.controls {
  position: absolute;
  bottom: 0;
  display: flex;
  justify-content: center;
  width: 100%;
}
.controls button {
  margin: 0 8px 12px;
  transition: var(--transition);
}
.controls button.active {
  background: var(--primary-color);
  color: var(--white);
}
</style>
