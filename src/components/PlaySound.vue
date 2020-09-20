<template>
  <Button
    variant="outline-primary"
    :class="{ glow: animation }"
    @click.native="animation = !animation"
  >
    Play Sound
  </Button>
</template>
<script>
import { Button } from "./Inputs";
export default {
  name: "PlaySound",
  components: {
    Button
  },
  data: function() {
    return {
      animation: false
    };
  }
};
</script>
<style scoped>
.glow {
  position: relative;
  z-index: 0;
}

.glow:before {
  content: "";
  background: linear-gradient(
    45deg,
    #ff0000,
    #ff7300,
    #fffb00,
    #48ff00,
    #00ffd5,
    #002bff,
    #7a00ff,
    #ff00c8,
    #ff0000
  );
  position: absolute;
  top: -2px;
  left: -2px;
  background-size: 400%;
  z-index: -1;
  filter: blur(5px);
  width: calc(100% + 4px);
  height: calc(100% + 4px);
  animation: glowing 20s linear infinite;
  opacity: 0;
  transition: opacity 0.3s ease-in-out;
}

.glow {
  color: var(--dark);
  font-weight: bold;
}

.glow:after {
  background: transparent;
}

.glow:before {
  opacity: 1;
}

.glow:after {
  z-index: -1;
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
}

@keyframes glowing {
  0% {
    background-position: 0 0;
  }
  50% {
    background-position: 400% 0;
  }
  100% {
    background-position: 0 0;
  }
}
</style>
