<template>
  <div id="app">
    <h1 class="app_title">Events</h1>
    <div class="app__forms-container">
      <SearchForm />
      <button class="app__btn" type="button" @click="handleOpenPopup">create</button>
    </div>
    <div class="app__events">
      <div class="app__events-container" >
        <EventsList
          :eventDates="eventDates"
          :events="events"
          @show-event="showEvent"
        />
      </div>
      <EventFullInfo :selectedEvent="selectedEvent"/>
    </div>
    <PopupWithForm
      @add-event="addEvent"
      v-if="isOpened"
      :handleClosePopup="handleClosePopup"
    />
  </div>
  <!--<router-view/>-->
</template>

<script>
import EventsList from '@/components/EventsList'
import EventFullInfo from '@/components/EventFullInfo'
import SearchForm from '@/components/SearchForm'
import PopupWithForm from '@/components/PopupWithForm'
export default {
  name: 'app',
  data () {
    return {
      events: [
        {
          id: 1,
          title: 'Monthly catch-up',
          category: 'light',
          description: 'https://zoom.us/i/1983475281',
          dateStart: {
            date: '12/27/2021',
            time: '8:30'
          },
          dateEnd: {
            date: '12/27/2021',
            time: '9:00'
          },
          checked: false,
          repeat: '',
          participants: ''
        },
        {
          id: 2,
          title: 'Quarterly review',
          category: 'hard',
          description: '',
          dateStart: {
            date: '12/15/2021',
            time: '8:30'
          },
          dateEnd: {
            date: '12/15/2021',
            time: '9:00'
          },
          checked: false,
          repeat: '',
          participants: ''
        },
        {
          id: 3,
          title: 'Presentation of new products and cost structure',
          category: 'medium',
          description: 'https://zoom.us/i/1983475281',
          dateStart: {
            date: '12/7/2021',
            time: '8:30'
          },
          dateEnd: {
            date: '12/7/2021',
            time: '9:00'
          },
          checked: false,
          repeat: '',
          participants: ''
        }
      ],
      isOpened: false,
      eventDates: [],
      selectedEvent: [{
        id: 3,
        title: 'Presentation of new products and cost structure',
        category: 'medium',
        description: 'https://zoom.us/i/1983475281',
        dateStart: {
          date: '12/7/2021',
          time: '8:30'
        },
        dateEnd: {
          date: '12/7/2021',
          time: '9:00'
        },
        checked: false,
        repeat: '',
        participants: ''
      }]
    }
  },
  mounted () {
    const arr = Array.from(new Set(this.events.map((event) => {
      return event.dateStart.date
    })))

    this.eventDates = arr.sort(function (a, b) {
      a = new Date(a)
      b = new Date(b)
      return a > b ? 1 : a < b ? -1 : 0
    })
  },
  components: {
    EventsList,
    EventFullInfo,
    SearchForm,
    PopupWithForm
  },
  methods: {
    handleOpenPopup () {
      this.isOpened = !this.isOpened
    },
    handleClosePopup () {
      this.isOpened = !this.isOpened
    },
    addEvent (event) {
      this.events.push(event)
      this.handleClosePopup()
    },
    showEvent (element) {
      this.selectedEvent = this.events.filter((event) => {
        if (event.id === Number(element.id)) {
          return event
        }
      })
    }
  }
}

</script>

<style lang="less">
#app {
  font-family: 'Roboto', Avenir, Helvetica, Arial, sans-serif;
  font-style: normal;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  position: relative;
  color: #2c3e50;
  background: #E5E5E5;
  height: 100vh;
  display: flex;
  flex-direction: column;
}

.app_title {
  margin: 68px 0 0;
  padding-left: 207px;
  align-self: flex-start;
  font-weight: 500;
  font-size: 24px;
  line-height: 28px;
}

.app__forms-container {
  max-width: 1068px;
  margin-top: 41px;
  padding-left: 207px;
  display: flex;
  flex-direction: row;
}

.app__btn {
  box-sizing: border-box;
  padding: 14px 100px;
  margin-left: auto;
  border: none;
  outline: none;
  justify-self: flex-end;
  background: #3B82F6;
  border-radius: 4px;
  color: #FFFFFF;
  font-weight: 700;
  font-size: 16px;
  line-height: 19px;
  text-transform: uppercase;
}

.app__events {
  max-width: 1068px;
  height: 64%;
  margin-top: 41px;
  padding-left: 207px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.app__events-container {
  margin: 0;
  padding: 20px 21px 19px 28px;
  background: #FFFFFF;
  overflow-y: scroll;
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
