<template>
  <div class="home">
    <!--img alt="Vue logo" src="../assets/logo.png" /-->
    <!--HelloWorld msg="Welcome to Your Vue.js App" /-->
    <TodoList />
  </div>
</template>

<script>
  import TodoList from "../components/TodoList.vue";

  export default {
    components: {
      TodoList,
    },
  };
</script>