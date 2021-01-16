<template>
  <div id="app">
    <appLeftSide @add="todoAddBtn()">
      <app-todo-list
        v-for="(item, index) in todoList"
        :key="index"
        :id='index'
        :item="item.todo"
        @change="todoEditBtn(index)"
        @remove="removeTodo(index)"
      ></app-todo-list>
    </appLeftSide>
    <app-right-side @save="saveButton()" v-if="isOpen" v-model="inputValue"></app-right-side>
  </div>
</template>


<script>
import leftSide from "./components/app-left-side.vue";
import todoList from "./components/app-todo-list.vue";
import rightSide from "./components/app-right-side.vue";

export default {
  data() {
    return {
      todoList: [{ todo: "Todo задачник измените и начните ставить задачи" }],
      inputValue: "",
      isOpen: false,
      isEdit: false,
      todoNum: 0
    };
  },

  components: {
    appLeftSide: leftSide,
    appTodoList: todoList,
    appRightSide: rightSide
  },

  methods: {
    // Save button
    saveButton() {
      if (this.isEdit == false) {
        this.addTodo();
      } else {
        this.editTodo();
      }
    },

    // Todo add
    addTodo() {
      if (this.inputValue.trim()) {
        this.todoList.push({
          todo: this.inputValue
        });
        this.inputValue = "";
      }
      this.isOpen = false;
    },

    // Todo edit
    editTodo() {
      this.todoList[this.todoNum].todo = this.inputValue;
      this.inputValue = "";
      this.isOpen = false;
    },

    // remove todo list
    removeTodo(index) {
      this.todoList.splice(index, 1);
      if (this.isOpen) {
        this.inputValue = "";
        this.isOpen = false;
      }
    },

    // Edit todo list button
    todoEditBtn(index) {
      this.isOpen = true;
      this.isEdit = true;
      this.inputValue = this.todoList[index].todo;
      this.todoNum = index;
    },

    // Add todo list button
    todoAddBtn() {
      this.isOpen = true;
      this.isEdit = false;
    }
  }
};
</script>

<style lang="scss">
#app {
  display: flex;
  justify-content: space-between;
  padding: 35px 26px 35px 51px;
}
</style>