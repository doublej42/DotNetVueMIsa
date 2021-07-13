<template>
  <div>
    <h2>This is just HTML</h2>
    <h3>{{ subtitle }}</h3>
    <!-- just html -->
    <p>
      My name is <strong>{{ name }}</strong>
    </p>
    <!-- can have variable displayed -->
    <p>
      Length: <strong>{{ lengthOfName }}</strong>
    </p>
    <ul>
      <li v-for="book in books" :key="book">{{ book }}</li>
    </ul>
    <v-text-field v-model="name" solo />
    <!-- user other components like a text field from Vuetify, this one is reactive -->
    <v-btn @click="reverseName" color="primary">Reverse Name</v-btn>
  </div>
</template>


<script lang="ts">
//https://class-component.vuejs.org/guide/class-component.html
//https://github.com/kaorun343/vue-property-decorator
import { Component, Vue, Prop } from 'vue-property-decorator'

@Component({})
export default class SimpleComponent extends Vue {
  //All the code for your component goes here
  //Data / state
  private name = 'Your Name Here'
  private books = ['The Martian', 'War of the Spark']

  //Computed are like data that always return the live results
  get lengthOfName() {
    return this.name.length
  }

  //methods perform actions but don't usually return data. Data is returned from the state.
  reverseName() {
    this.name = this.name.split('').reverse().join('')
  }

  @Prop({ default: 'default subtitle', required: true, type: String }) readonly subtitle!: string
}
</script>
