<template>
  <Button
    type="button"
    variant="outline-primary"
    :class="{ glow: active }"
    @click.native="active = !active"
  >
    {{ text }}
  </Button>
</template>
<script>
import { Button } from "./FormElements";
export default {
  name: "PlaySound",
  components: {
    Button
  },
  data: function() {
    return {
      text: "Play Sound",
      active: false
    };
  },
  watch: {
    active: function() {
      this.text = this.active ? "Stop Sound" : "Play Sound";
    }
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
    #fffb00,
    #48ff00,
    #00ffd5,
    #002bff,
    #7a00ff,
    #ff00c8,
    #fffb00
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
