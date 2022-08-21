<template>
  <div
    @dragenter.prevent="toggleActive"
    @dragleave.prevent="toggleActive"
    @drop.prevent="toggleActive"
    @dragover.prevent
    class="dropzone page-flex"
    :class="{ active: activeDropzone }"
  >
    <span>Drag and Drop File</span>
    <span>OR</span>
    <label for="dropzoneFile" class="cursor-pointer">Select File</label>
    <input type="file" id="dropzoneFile" class="dropzoneFile" />
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  name: "DropzoneComponent",
  setup() {
    const activeDropzone = ref(false);
    const toggleActive = () => {
      activeDropzone.value = !activeDropzone.value;
    };

    return { activeDropzone, toggleActive };
  },
};
</script>

<style lang="scss" scoped>
@use "../styles/mixin/_colors.scss" as colors;

.dropzone {
  width: 350px;
  height: 200px;
  flex-direction: column;
  row-gap: 16px;
  border: 2px solid colors.$primary;
  background-color: colors.$white;
  transition: 0.3s ease all;

  label {
    padding: 6px 9px;
    color: colors.$white;
    background-color: colors.$success-primary;
    transition: 0.3s ease all;
    border-radius: 5px;
  }

  input {
    display: none;
  }

  &.active {
    color: colors.$white;
    background-color: colors.$success-primary;
    border-color: colors.$white;

    label {
      background-color: colors.$white;
      color: colors.$success-primary;
    }
  }
}
</style>
