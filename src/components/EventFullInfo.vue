<template>
  <div class="info">
    <h2 class="info__title">{{selectedEvent[0].title}}</h2>
    <div class="info__container">
      <p class="info__date">{{selectedEvent[0].dateStart.date}}</p>
      <div :class="['info__category', `${selectedEvent[0].category}`]"></div>
      <p class="info_time">{{selectedEvent[0].dateStart.time}} - {{selectedEvent[0].dateEnd.time}}</p>
    </div>
    <div class="info__participants">
      <div class="info__participant">
        <img class="info__avatar" src="../images/avatar.jpg" />Michael K.
      </div>
      <div class="info__participant">
        <img class="info__avatar" src="../images/avatar.jpg" />Sally D.</div>
    </div>
    <p class="info__description">{{selectedEvent[0].description}}
    </p>
  </div>
</template>

<script>
export default {
  props: ['selectedEvent']
}
</script>

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

.light {
  background: #3B82F6;
}

.medium {
  background: #FBBF24;
}

.hard {
  background: #EC4899;
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
