<template>
  <HelloWorld msg="hello world" />
  <button @click="isShow = !isShow">show</button>
  <button @click="handleMsg">handleMSg</button>
  <Study v-if="isShow" :msg="this.message" />
</template>

<script lang="ts">
import { defineComponent, reactive, ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
// import Study from "./components/Study01.vue";
import Study from "./components/Study02.vue";
export default defineComponent({
  name: "App",
  components: {
    HelloWorld,
    Study,
  },
  setup() {
    let isShow = ref<boolean>(true);
    let message = ref("");
    const handleMsg = () => {
      console.log("aaaa");
      const aa = Math.random();
      console.log(aa);
      message.value = +aa;
    };
    return {
      isShow,
      message,
      handleMsg,
    };
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
