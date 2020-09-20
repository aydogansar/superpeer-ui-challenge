<template>
  <form class="settings-form" @submit="handleSubmit">
    <FormInput
      input="TextBox"
      class="mt-4 mb-5"
      icon="user"
      v-model="formStates.name"
    />
    <FormInput
      input="SelectBox"
      ref="camera"
      class="mt-2 mb-2"
      title="Camera"
      v-model="formStates.camera"
      :options="cameraOptions"
    />
    <FormInput
      input="SelectBox"
      ref="speaker"
      class="mt-2 mb-2"
      title="Speaker"
      v-model="formStates.speaker"
      :options="speakerOptions"
    />
    <FormInput
      input="SelectBox"
      ref="mic"
      class="mt-2 mb-2"
      title="Microphone"
      v-model="formStates.mic"
      :options="micOptions"
    />
    <FormInput
      input="Button"
      class="mt-2 mb-2"
      title="Sound Test"
      text="Play Sound"
      variant="outline-primary"
    />
    <FormInput input="Button" class="mt-5" text="Join Call" />
  </form>
</template>
<script>
import FormInput from "./FormInput";

export default {
  name: "SettingsForm",
  components: {
    FormInput
  },
  data: function() {
    return {
      cameraOptions: ["Facetime HD Camera"],
      speakerOptions: ["Built-in Output (Headphone)"],
      micOptions: ["Built-in Microphone"],
      formStates: {
        name: "",
        camera: "",
        speaker: "",
        mic: ""
      }
    };
  },
  methods: {
    handleSubmit: function(e) {
      e.preventDefault();
      console.log(this.formStates);
    }
  },
  mounted() {
    this.formStates.mic = this.$refs.mic.$options.propsData.options[0];
    this.formStates.camera = this.$refs.camera.$options.propsData.options[0];
    this.formStates.speaker = this.$refs.speaker.$options.propsData.options[0];
  }
};
</script>
<style scoped>
.settings-form {
  width: 100%;
}
</style>
