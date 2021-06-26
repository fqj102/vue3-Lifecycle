<template>
  <h2>lifecycle</h2>
  <div>study02</div>
  <div>{{ msg }}</div>
</template>
<script>
import {
  defineComponent,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
} from "vue";

export default defineComponent({
  name: "Study02",
  props: {
    msg: String,
  },
  beforeCreate() {
    console.log("2.x beforeCreate");
  },
  created() {
    console.log("2.x created");
  },
  beforeUpdate() {
    console.log("2.x beforeUpdate");
  },
  mounted() {
    console.log("2.x mounted");
  },
  updated() {
    console.log("2.x updated");
  },
  beforeUnmount() {
    console.log("2.x beforeDestory==>beforeUnmouted");
  },
  unmounted() {
    console.log("2.x destroyed==>umounted");
  },

  setup() {
    console.log("3.x setup--->2.x beforeCreated,created");

    onBeforeMount(() => {
      console.log("3.x onBeforeMount");
    });
    onMounted(() => {
      console.log("3.x onMounted");
    });
    onBeforeUpdate(() => {
      console.log("3.x onBeforeUpdate");
    });
    onUpdated(() => {
      console.log("3.x onUpdated");
    });
    onBeforeUnmount(() => {
      console.log("3.x onBeforeUnmount");
    });
    onUnmounted(() => {
      console.log("3.x onUnmounted");
    });
  },
});
</script>
