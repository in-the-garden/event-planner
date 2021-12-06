<template>
  <div id="app">
    <div class="app__events-container">
      <EventsList
        v-bind:events="events"
      />
      <EventFullInfo />
    </div>
    <!--<router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>-->
  </div>
  <!--<router-view/>-->
</template>

<script>
import EventsList from '@/components/EventsList'
import EventFullInfo from '@/components/EventFullInfo'
export default {
  name: 'app',
  data () {
    return {
      events: [
        { id: 1, title: 'Monthly catch-up', category: {}, description: 'https://zoom.us/i/1983475281', dateStart: '8:30 - 9:00 AM', dateEnd: '8:30 - 9:00 AM', repeat: false, repeatType: {}, participants: '' },
        { id: 2, title: 'Quarterly review', category: {}, description: '', dateStart: '8:30 - 9:00 AM', dateEnd: '8:30 - 9:00 AM', repeat: false, repeatType: {}, participants: '' },
        { id: 3, title: 'Presentation of new products and cost structure', category: {}, description: 'https://zoom.us/i/1983475281', dateStart: '8:30 - 9:00 AM', dateEnd: '8:30 - 9:00 AM', repeat: false, repeatType: {}, participants: '' }
      ]
    }
  },
  components: {
    EventsList,
    EventFullInfo
  }
}

</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: #E5E5E5;
  height: 100vh;
  display: flex;
  flex-direction: column;
}

.app__events-container {
  max-width: 1068px;
  margin-top: 41px;
  align-self: center;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
