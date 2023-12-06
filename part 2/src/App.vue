<script>
import Accordion from './components/Accordion.vue'

export default {
  components: {
    Accordion
  },
  data() {
    return {
      newAccordion: {
        name: '',
        section: ''
      },
      accordions: []
    }
  },
  methods: {
    add() {
      if (!this.newAccordion.name || !this.newAccordion.section) {
        alert('All fields are required')
        return
      }
      if (this.accordions.map(item => item.name).includes(this.newAccordion.name)) {
        alert('The accordion with same name is already exists')
        return
      }
      this.accordions.push({
        name: this.newAccordion.name,
        section: this.newAccordion.section
      })
      this.newAccordion = { name: '', section: '' }
    }
  }
}
</script>

<template>
<ul>
  <li v-for="accordion in accordions"> 
    <Accordion :accordion="accordion" />
  </li>
</ul>
<form @submit.prevent="add">
  <span>
    <label>name</label>
    <input type="text" v-model="newAccordion.name">
  </span>
  <span>
    <label>section</label>
    <textarea v-model="newAccordion.section"></textarea>
  </span>
  <span>
    <button>add</button>
  </span>
</form>
</template>