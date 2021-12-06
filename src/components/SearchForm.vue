<template>
  <form class="form">
    <button class="form__btn" type="submit"/>
    <input
      class="form__input"
      placeholder="Search"
    />
  </form>
</template>

<style lang="less">
.form {
  padding: 14px 12px;
  margin: 0;
  max-width: 238px;
  max-height: 44px;
  background: #FFFFFF;
  display: flex;
  flex-direction: row;
  justify-content: start;
  align-items: center;
  border-radius: 4px;
}
.form__btn {
  padding: 0;
  width: 16px;
  height: 16px;
  background-color: inherit;
  background-image: url('../images/search-btn.svg');
  background-position: center;
  border: none;
  outline: none;
}
.form__input {
  max-width: 100%;
  margin-left: 16px;
  padding: 0 0 2px 0;
  outline: none;
  border: none;
  font-weight: 400;
  font-size: 12px;
  line-height: 14px;
  box-sizing: border-box;
  color: #343A40;

  &:focus {
    border-bottom: 1px solid #3B82F6;
  }
}
</style>
