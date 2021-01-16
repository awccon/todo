<template>
  <div class="left-side">
    <h1>Список дел</h1>
    <h2 class="subtitle">Добавляете и редактируйте списки дел</h2>
    <slot></slot>
    <button class="add-button" @click="$emit('add')">
      Добавить
      дело
    </button>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
button {
  border: none;
  background-color: none;

  &:focus {
    outline: none;
  }
}

.left-side {
  width: 40%;
  margin: 0 auto;

  h1 {
    font-family: Quicksand, sans-serif;
    font-style: normal;
    font-weight: bold;
    font-size: 48px;
    line-height: 60px;
  }

  .subtitle {
    margin-top: 9px;
    margin-bottom: 20px;
    font-family: PTSans, sans-serif;
    font-style: normal;
    font-weight: normal;
    font-size: 14px;
    line-height: 18px;
  }

  button {
    font-family: Montserrat, sans-serif;
    font-style: normal;
    font-weight: bold;
    font-size: 9px;
    line-height: 11px;
    text-align: center;
    text-transform: uppercase;
    color: #ffffff;
    background-color: #bb6bd9;
    border-radius: 22px;
    border: 1px solid transparent;

    &:active {
      transition: 0.2s;
      transform: scale(0.9);
    }

    &:hover {
      border: 1px solid rgb(88, 66, 84);
    }
  }
}

.add-button {
  width: 139px;
  height: 44px;
  margin-top: 32px;
}
</style>