<template>
  <div>
    <h1>{{ heading }}</h1>
    <div v-for="(item, index) in todos" :key="index">
      <ul>
        <section>
          <h4>{{ item.userId }}</h4>
          <h4>{{ item.title }}</h4>
        </section>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodosComponent",
  data() {
    return {
      heading: "Todos from API",
      todos: [],
    };
  },
  mounted() {
    fetch("https://jsonplaceholder.typicode.com/todos/")
      .then((response) => response.json())
      .then((json) => (this.todos = json));
  },
};
</script>
