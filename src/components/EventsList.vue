<template>
  <div class="events">
    <ul class="events__container">
      <EventItem
        v-for="(event, idx) in events"
        :key="idx + 1"
        :event="event"
      />
    </ul>
  </div>
</template>

<script>
import EventItem from '@/components/EventItem'
export default {
  props: ['events'],
  components: {
    EventItem
  }
}
</script>

<style lang="less">
.events {
  margin: 0;
  padding: 28px 21px 19px 28px;
  background: #FFFFFF;
}

.events__container {
  margin: 0;
  padding: 0;
  width: 290px;
  display: flex;
  flex-direction: column;
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
