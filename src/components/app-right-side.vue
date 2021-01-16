<template>
  <div class="right-side">
    <div class="input-block">
      <h2>Что нужно сделать?</h2>
      <input
        type="text"
        placeholder="Побегать вечером"
        :value="value"
        @input="$emit('input', 
                $event.target.value)"
        @keyup.enter="$emit('save')"
        autofocus
      />
      <button class="save-button" @click="$emit('save')">СОХРАНИТЬ</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["value"]
};
</script>

<style lang="scss">
.right-side {
  width: 57%;
}

.input-block {
  box-sizing: border-box;
  width: 100%;
  height: 599px;
  padding: 25.44px 28px;
  background: #fafafa;
  box-shadow: 0px 15px 12px rgba(0, 0, 0, 0.22),
    0px 19px 38px rgba(0, 0, 0, 0.3);
  border-radius: 2px;

  h2 {
    font-family: Montserrat, sans-serif;
    font-style: normal;
    font-weight: bold;
    font-size: 12px;
    line-height: 15px;
    margin-bottom: 13px;
  }

  input {
    &:focus {
      outline: none;
    }

    padding: 11px 9px 9px 20px;
    margin-bottom: 25.56px;
    width: 320px;
    height: 44px;
    box-sizing: border-box;

    background: #ffffff;
    border: 1px solid rgba(31, 32, 65, 0.25);
    box-sizing: border-box;
    border-radius: 4px;

    &::placeholder {
      font-family: Montserrat, sans-serif;
      font-style: normal;
      font-weight: normal;
      font-size: 14px;
      line-height: 24px;
      color: rgba(31, 32, 65, 0.25);
    }
  }

  button {
    display: block;
    width: 114.35px;
    height: 36px;

    background: #ffffff;
    border: 1px solid #dbdbdb;
    border-radius: 2px;

    font-family: Roboto, sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 16px;
    text-align: center;
    letter-spacing: 0.0357143em;

    color: #bb6bd9;

    &:active {
      transition: 0.2s;
      transform: scale(0.9);
    }

    &:hover {
      border: 1px solid #1a1a1a;
    }
  }
}
</style>