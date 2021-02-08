<template>
  <div class="container">
    <Gif :msg="message" />
  </div>
</template>

<script>
import Gif from "./components/Gif.vue";
export default {
  components: { Gif },
  beforeMount() {
    this.created();
  },
  name: "App",
  data() {
    return {
      message: "Using Parcel In A Vue.js App",
    };
  },
  methods: {
    created() {
      this.message = process.env.NODE_ENV;
    },
  },
};
</script>

<style scoped>
.container {
  width: 600px;
  margin: 50px auto;
  text-align: center;
}
</style>