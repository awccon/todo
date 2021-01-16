<template>
  <div class="todo-item">
    <span class="todo-count">{{id + 1}}.</span>
    <div class="todo-label">{{item}}</div>
    <div class="buttons-wrap">
      <button class="change-button" @click="$emit('change')">Изменить</button>
      <button class="remove-button" @click="$emit('remove')">Удалить</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["id", "item"]
};
</script>

<style lang="scss">
.todo-item {
  display: flex;
  font-family: Quicksand, sans-serif;
  font-style: normal;
  font-weight: bold;
  font-size: 14px;
  line-height: 17px;
  padding-top: 12px;
  padding-bottom: 5px;
  border-bottom: 1px solid #cacaca;

  &:hover {
    .buttons-wrap {
      display: flex;
    }
  }
}

.todo-count {
  margin-right: 10px;
  line-height: 1.8;
}

.todo-label {
  width: 100%;
  line-height: 1.8;
}

/* BUTTON STYLES */
.buttons-wrap {
  width: 223px;
  height: 33px;
  display: none;
  margin-top: -9px;

  button {
    width: 104.25px;
    height: 33px;
  }
}

.change-button {
  left: 70px;
  top: -10px;
}

.remove-button {
  margin-left: 9.75px;
  left: 185px;
  top: -10px;
  background-color: #eb5757 !important;
}
</style>