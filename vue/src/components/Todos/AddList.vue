<template>
  <div id="AddList">
    <input type="text" v-model="tText" />
    <input type="button" value="추가" @click="addList" />
  </div>
</template>

<script>
export default {
  name: "AddList",
  props: {
    todos: Array,
  },
  methods: {
    addList() {
      const size = this.todos.length;
      const lastId = size === 0 ? size : this.todos[size - 1].id;
      //   console.log(size);
      //   console.log(lastId);
      const add = {
        id: lastId + 1,
        title: this.tText,
        completed: false,
      };
      this.todos.push(add);
    },
  },
  data() {
    return {
      tText: "",
    };
  },
};
</script>

<style scoped>
#AddList {
  width: 100%;
  display: flex;
}
input[type="text"] {
  width: 70%;
  height: 50px;
  font-size: 28px;
  padding: 0 20px;
}
input[type="button"] {
  width: 30%;
  font-size: 30px;
}
</style>