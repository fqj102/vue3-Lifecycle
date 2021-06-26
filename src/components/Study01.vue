<template>
  <div>study01</div>
  <div>
    <button @click="handleClick">click</button>
    {{ a }}
    <hr />
    reactive
    {{ user.firstname }} - {{ user.lastname }}
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, onMounted, onUpdated } from "vue";

export default defineComponent({
  name: "Study01",
  props: {
    msg: String,
  },

  setup() {
    onMounted(() => {
      console.log("Component is mounted!");
    });
    onUpdated(() => {
      console.log("Component is updated!");
    });
    const a = 1;
    interface IUser {
      firstname: string | null;
      lastname: string | null;
    }
    const user: IUser = reactive({
      firstname: null,
      lastname: null,
    });
    const handleClick = () => {
      console.log("click button");
      user.firstname = "fang1";
      user.lastname = "qingji";
    };

    return {
      a,
      handleClick,
      user,
    };
  },
});
</script>
