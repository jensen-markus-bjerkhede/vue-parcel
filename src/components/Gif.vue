<template>
  <div v-if="isDev()">
    <div class="dev"></div>
    <h1>dev mode</h1>
  </div>
  <div v-else>
    <img src="" alt="Kitten" />
    <h1>prod mode</h1>
  </div>
</template>

<script>
export default {
  name: "Gif",
  methods: {
    isDev() {
      return process.env.NODE_ENV === "dfs";
    },
  },
  mounted() {
    let myImage = document.querySelector("img");

    fetch("https://placekitten.com/100/100")
      .then((response) => response.blob())
      .then((myBlob) => {
        myImage.src = URL.createObjectURL(myBlob);
      });
  },
  data() {
    return {};
  },
};
</script>
<style scoped>
.dev {
  height: 100px;
  width: 100px;
  background-color: #555;
}
</style>