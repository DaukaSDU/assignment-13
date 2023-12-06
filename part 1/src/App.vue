<script>
import TimeLine from './components/TimeLine.vue'

export default {
  components: {
    TimeLine
  },
  data() {
    return {
      events: [],
      newEvent: {
        title: '',
        desc: '',
        date: null
      }
    }
  },
  methods: {
    addEvent() {
      this.events.push({ 
                          title: this.newEvent.title,
                          desc: this.newEvent.desc,
                          date: this.newEvent.date
                        })
      this.newEvent.title = ''
      this.newEvent.desc = ''
    }
  }
}
</script>

<template>
  <form @submit.prevent="addEvent()">
    <span>
      <label>Event Title</label>
      <input type="text" v-model="newEvent.title">
    </span>
    <span>
      <label>Event Description</label>
      <textarea v-model="newEvent.desc"></textarea>
    </span>
    <span>
      <label>Date</label>
      <input type="date" v-model="newEvent.date">
    </span>
    <span>
      <button>Submit</button>
    </span>
  </form>
  <hr>
  <ul>
    <li v-for="event in events">
      <TimeLine :event="event" />
    </li>
  </ul>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

form {
  margin: 10px;
  display: flex;
  justify-content: space-around;
}

form>span {
  display: flex;
  flex-direction: column;
}
</style>