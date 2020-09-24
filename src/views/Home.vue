<template>
  <TodoList/>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import TodoList from "@/components/TodoList.vue";
export default {
  name: "Home",
  components: {
    TodoList,
  },
  data: () => ({}),
};
</script>
