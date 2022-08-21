<template>
  <div class="home page-flex">
    <h1>Upload File</h1>
    <DropZone @drop.prevent="handleDrop" @change="handleSelect" />
    <span v-if="dropzoneFile" class="file-info"
      >File: {{ dropzoneFile.name }}</span
    >
  </div>
</template>

<script>
import DropZone from "../components/DropZone.vue";
import { ref } from "vue";

export default {
  name: "HomeView",
  components: { DropZone },
  setup() {
    let dropzoneFile = ref("");
    const handleDrop = (e) => {
      dropzoneFile.value = e.dataTransfer.files[0];
    };

    const handleSelect = () => {
      dropzoneFile.value = document.querySelector(".dropzoneFile").files[0];
    };
    return { dropzoneFile, handleDrop, handleSelect };
  },
};
</script>

<style lang="scss" scoped>
@use "../styles/mixin/_colors.scss" as colors;

.home {
  flex-direction: column;
  background-color: colors.$background;
  h1 {
    font-size: 36px;
    margin-bottom: 24px;
  }
  .file-info {
    margin-top: 18px;
  }
}
</style>
