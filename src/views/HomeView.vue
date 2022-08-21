<template>
  <div class="home page-flex">
    <h1>DropZone</h1>
    <DropZone />
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

    return { dropzoneFile };
  },
};
</script>

<style lang="scss" scoped>
@use "../styles/mixin/_colors.scss" as colors;

.home {
  flex-direction: column;
  background-color: colors.$white;
  h1 {
    font-size: 36px;
    margin-bottom: 24px;
  }
  .file-info {
    margin-top: 18px;
  }
}
</style>
