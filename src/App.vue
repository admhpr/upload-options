<template>
  <div id="app">
    <UploadContainer />
  </div>
</template>

<script>
import UploadContainer from "./containers/UploadContainer";

export default {
  name: "App",
  components: {
    UploadContainer,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
