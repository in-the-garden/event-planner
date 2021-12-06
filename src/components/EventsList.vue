<template>
  <div class="events" v-for="(eventDate, idx) in eventDates" :key="idx + 1">
    <ul class="events__container"> {{eventDate}}
      <EventItem
        v-for="(event, idx) in events.filter((event) => {if (event.dateStart.date === eventDate) { return event}})"
        :key="idx + 1"
        :event="event"
      />
    </ul>
  </div>
</template>

<script>
import EventItem from '@/components/EventItem'
export default {
  props: ['eventDates', 'events'],
  components: {
    EventItem
  }
}
</script>

<style lang="less">
.events {

}

.events__container {
  margin: 8px 0 0;
  padding: 0;
  width: 290px;
  display: flex;
  flex-direction: column;
  font-family: 'Inter', Avenir, Helvetica, Arial, sans-serif;
  font-weight: 400;
  font-size: 13px;
  line-height: 20px;
  color: #868E96;

}

.event {
  list-style: none;
}

.event__time {
  margin: 0;
}

.event__title {
  margin: 0;
}

.event__description {
  margin: 0;
}
</style>
