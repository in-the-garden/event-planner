<template>
  <div class="info">
    <h2 class="info__title">Quarterly review</h2>
    <div class="info__container">
      <p class="info__date">TODAY 2/27/2021</p>
      <div class="info__category"></div>
      <p class="info_time">8:30 - 9:00 AM</p>
    </div>
    <div class="info__participants">
      <div class="info__participant">
        <img class="info__avatar" src="../images/avatar.jpg" />Michael K.
      </div>
      <div class="info__participant">
        <img class="info__avatar" src="../images/avatar.jpg" />Sally D.</div>
    </div>
    <p class="info__description">Your application is rejected!
      You submitted on your Letter of Authorization (LOA) is different from what is on file with your carrier in their Customer Service Record (CSR). A CSR is a copy of how your telephone records appear in the telephone company’s database.
      https://zoom.us/i/1983475281
    </p>
  </div>
</template>

<style lang="less">
.info {
  width: 700px;
  margin-left: 28px;
  padding: 20px 20px 20px 25px;
  background: #FFFFFF;
  display: flex;
  flex-direction: column;
}

.info__title {
  margin: 0;
  text-align: start;
  font-family: 'Inter', Avenir, Helvetica, Arial, sans-serif;
  font-weight: 500;
  font-size: 16px;
  line-height: 16px;
}

.info__container {
  padding: 6px 0 13px;
  display: flex;
  flex-direction: row;
  text-align: start;
  align-items: center;
  border-bottom: 1px solid #ECF0F2;
}

.info__date {
  margin: 0;
}

.info__category {
  margin-left: 18px;
  width: 12px;
  height: 12px;
  border-radius: 100%;
  background: #3B82F6;
}

.info_time {
  margin: 0 0 0 8px;
}

.info__participants {
  padding: 21px 0 18px;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  border-bottom: 1px solid #ECF0F2;
}

.info__participant {
  margin-left: 26px;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;

  &:first-of-type {
    margin: 0;
  }
}

.info__avatar {
  width: 33px;
  height: 33px;
  border-radius: 100%;
  object-position: center;
  object-fit: cover;
}

.info__description {
  text-align: start;
}
</style>
