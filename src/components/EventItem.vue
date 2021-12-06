<template>
   <li class="event">
     <div class="event__category"></div>
     <article class="event__info">
      <p class="event__time">{{event.dateStart.time}} - {{event.dateEnd.time}}</p>
      <h2 class="event__title">{{event.title}}</h2>
      <p class="event__description">{{event.description}}</p>
     </article>
   </li>
</template>

<script>
export default {
  props: {
    event: Object
  },
  filters: {
    setTime (value) {
      const arr = value.split('T')
      return arr[1]
    }
  }
}
</script>

<style lang="less">
.event {
  font-family: 'Inter', Avenir, Helvetica, Arial, sans-serif;
  list-style: none;
  display: flex;
  flex-direction: row;
}
.event__category {
  width: 12px;
  height: 12px;
  border-radius: 100%;
  background: #3B82F6;
}
.event__info {
  margin-left: 8px;
  display: flex;
  flex-direction: column;
  color: #333333;
}
.event__time {
  margin: 0;
  text-align: start;
  font-weight: 600;
  font-size: 11px;
  line-height: 16px;
}
.event__title {
  margin: 0;
  text-align: start;
  font-weight: 500;
  font-size: 12px;
  line-height: 16px;
  color: #BDBDBD;
}
.event__description {
  margin: 0;
  text-align: start;
  font-weight: 400;
  font-size: 11px;
  line-height: 16px;
}
</style>
