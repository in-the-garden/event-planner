<template>
  <div class="popup">
    <form class="popup__form">
      <h2 class="popup__name">Create event</h2>
      <table>
        <tr>
          <td>
            <label>Title</label>
            <input class="popup__title" placeholder="Title"/>
            <label>Category</label>
            <select class="popup__category" id="category" name="category">
              <option value="">Category</option>
              <option value="light">Light</option>
              <option value="medium">Medium</option>
              <option value="hard">Hard</option>
            </select>
            <input class="popup__category" placeholder="Category"/>
            <label>Description</label>
            <textarea class="popup__description" rows="5" placeholder="Description"/>
          </td>
          <td>
            <label>Date</label>
            <input class="popup__date" type="date" placeholder="DataTime"/>
            <div class="popup__checkbox">
              <input type="checkbox" name="repeat" id="repeat" value="repeat">
              <label for="repeat">Repeat</label>
            </div>
            <label>Participants</label>
            <input class="popup__participants" placeholder="Participants"/>
          </td>
        </tr>
      </table>
      <button class="popup__btn">create</button>
    </form>
  </div>
</template>

<style lang="less">
@text-color: #333333;

table {
  margin-top: 89px;
}

tr {
  display: flex;
  flex-direction: row;
}

td {
  box-sizing: border-box;
  width: 301px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;

  &:last-of-type {
    margin-left: 39px;
  }
}

label {
  margin-top: 29px;
  text-align: start;
  color: @text-color;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;

  &:first-of-type {
    margin-top: 0;
  }
}

input, textarea {
  box-sizing: border-box;
  font-family: 'Roboto', Avenir, Helvetica, Arial, sans-serif;
  margin: 14px 0 0;
  padding: 12px 0 13px 16px;
  width: 301px;
  border: 1px solid #4F4F4F;
  border-radius: 8px;
  color: @text-color;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
}

.popup {
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(0, 0, 0, .5);
  z-index: 1;
}

.popup__form {
  width: 700px;
  padding: 0 27px 32px 32px;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  background: #FFFFFF;
  position: relative;
  box-sizing: border-box;
}

.popup__name {
  margin: 0;
  font-family: 'Inter', Avenir, Helvetica, Arial, sans-serif;
  font-weight: 500;
  font-size: 18px;
  line-height: 16px;
  color: @text-color;
  position: absolute;
  top: 20px;
  left: 25px;
}

.popup__checkbox {
  margin-top: 29px;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
}

#repeat {
  margin: 0 11px;
  width: 20px;
  height: 20px;
}

.popup__btn {
  font-family: 'Roboto', Avenir, Helvetica, Arial, sans-serif;
  width: max-content;
  align-self: center;
  margin-top: 58px;
  padding: 15px 100px;
  text-transform: uppercase;
  font-weight: 700;
  font-size: 16px;
  line-height: 19px;
  box-sizing: border-box;
  border: none;
  border-radius: 4px;
  background: #3B82F6;
  color: #FFFFFF;
}
</style>
