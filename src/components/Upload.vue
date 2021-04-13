<template>
  <div>
    <vue-dropzone id="dropzone" :key="componentKey" :options="options" />
    <section class="options">
      <tbody>
        <tr v-for="(v, k) in options" :key="k">
          <td>{{ k }}</td>
          <td>{{ v }}</td>
        </tr>
      </tbody>
      <section class="options">
        <label for="onlyDicoms">only DICOMs</label>
        <input type="checkbox" id="onlyDicoms" v-model="onlyDicoms" />
      </section>
    </section>
  </div>
</template>

<script>
import VueDropzone from "vue2-dropzone";
import "vue2-dropzone/dist/vue2Dropzone.min.css";
export default {
  name: "Upload",
  data() {
    return {
      defaultOptions: {
        url: "https://httpbin.org/post",
        thumbnailWidth: 300,
        headers: { "an-example": "header value" },
        addRemoveLinks: true,
      },
      onlyDicoms: false,
      componentKey: 0,
    };
  },
  components: {
    VueDropzone,
  },
  computed: {
    options() {
      const additional = this.onlyDicoms
        ? {
            acceptedFiles: ".dcm,.zip",
          }
        : {};
      return { ...this.defaultOptions, ...additional };
    },
  },
  watch: {
    onlyDicoms(v) {
      this.componentKey += 1;
    },
  },
};
</script>
<style scoped>
table {
  border-collapse: collapse;
}
table,
th,
td {
  border: 1px solid black;
  text-align: left;
  padding: 0.5em;
}
#dropzone,
#dropzone-2 {
  border: 2px solid #E5E5E5;
  padding: 100px;
  font-family: "Arial", sans-serif;
  letter-spacing: 0.2px;
  color: #777;
  transition: 0.2s linear;
}
.options {
  display: flex;
  justify-content: space-evenly;
  margin-top: 3em;
}
</style>
