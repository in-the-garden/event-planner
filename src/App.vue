<template>
  <div id="app">
    <div class="app__forms-container">
      <SearchForm />
      <button class="app__btn" type="button" @click="handleOpenPopup">create</button>
    </div>
    <div class="app__events-container">
      <EventsList
        :events="events"
      />
      <EventFullInfo />
    </div>
    <PopupWithForm v-if="isOpened" :handleClosePopup="handleClosePopup"/>
    <!--<router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>-->
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
        { id: 1, title: 'Monthly catch-up', category: {}, description: 'https://zoom.us/i/1983475281', dateStart: '8:30 - 9:00 AM', dateEnd: '8:30 - 9:00 AM', repeat: false, repeatType: {}, participants: '' },
        { id: 2, title: 'Quarterly review', category: {}, description: '', dateStart: '8:30 - 9:00 AM', dateEnd: '8:30 - 9:00 AM', repeat: false, repeatType: {}, participants: '' },
        { id: 3, title: 'Presentation of new products and cost structure', category: {}, description: 'https://zoom.us/i/1983475281', dateStart: '8:30 - 9:00 AM', dateEnd: '8:30 - 9:00 AM', repeat: false, repeatType: {}, participants: '' }
      ],
      isOpened: false
    }
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

.app__forms-container {
  max-width: 1068px;
  margin-top: 41px;
  padding-left: 207px;
  display: flex;
  flex-direction: row;
}

.app__btn {
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

.app__events-container {
  max-width: 1068px;
  height: 64%;
  margin-top: 41px;
  padding-left: 207px;
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
