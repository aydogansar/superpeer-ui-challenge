<template>
  <form class="settings-form" @submit="handleSubmit">
    <FormInput input="TextBox" class="mt-4 mb-4" icon="user" />
    <FormInput
      input="SelectBox"
      class="mt-2 mb-2"
      title="Camera"
      :options="cameraOptions"
    />
    <FormInput
      input="SelectBox"
      class="mt-2 mb-2"
      title="Speaker"
      :options="speakerOptions"
    />
    <FormInput
      input="SelectBox"
      class="mt-2 mb-2"
      title="Microphone"
      :options="micOptions"
    />
    <FormInput
      input="Button"
      class="mt-2 mb-2"
      title="Sound Test"
      text="Play Sound"
      variant="outline-primary"
    />
    <FormInput input="Button" class="mt-4" text="Join Call" />
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
      micOptions: ["Built-in Microphone (E)"]
    };
  },
  methods: {
    handleSubmit: function(e) {
      e.preventDefault();
    }
  }
};
</script>
<style scoped>
.settings-form {
  width: 100%;
}
</style>
