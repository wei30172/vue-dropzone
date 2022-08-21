<template>
  <div class="dropzone page-flex">
    <span>Drag File</span>
    <span>OR</span>
    <label for="dropzoneFile" class="cursor-pointer">Select File</label>
    <input type="file" id="dropzoneFile" class="dropzoneFile" />
  </div>
</template>

<script>
export default {
  name: "DropzoneComponent",
};
</script>

<style lang="scss" scoped>
@use "../styles/mixin/_colors.scss" as colors;

.dropzone {
  width: 360px;
  height: 180px;
  flex-direction: column;
  row-gap: 16px;
  border: 3px dashed colors.$success-primary;
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
}
</style>
