<template>
  <div class="video-call">
    <div class="controls">
      <IconButton icon="mic" class="shadow" />
      <IconButton icon="camera" class="shadow" />
      <IconButton icon="options" class="shadow" />
    </div>
  </div>
</template>
<script>
import IconButton from "./IconButton";

export default {
  name: "VideoCall",
  components: {
    IconButton
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
  margin-top: 20px;
  position: relative;
}
.controls {
  position: absolute;
  bottom: 0;
  display: flex;
  justify-content: center;
  width: 100%;
  padding-bottom: 10px;
}
.controls button {
  margin: 0 10px;
}
</style>
