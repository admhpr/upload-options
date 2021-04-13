<template>
  <div>
    <h3>Dropzone</h3>
    <Upload />
    <hr />
    <h3>Native File</h3>
    <input type="file" name="avatar" accept=".dcm" multiple />
    <hr />
    <h3>Native Folder</h3>
    <input type="file" name="avatar" accept=".dcm" multiple webkitdirectory />
    <hr />
  </div>
</template>

<script>
import Upload from "../components/Upload";
export default {
  name: "UploadContainer",
  components: {
    Upload,
  },
};
</script>

<style scoped>
h3 {
  display: flex;
  justify-content: flex-start;
}
</style>
