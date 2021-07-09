<template>
  <v-container fluid>
    <!-- always have one tag at the top level -->
    <v-slide-y-transition mode="out-in">
      <v-row>
        <v-col>
          <h2>This is just HTML</h2>
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
        </v-col>
      </v-row>
    </v-slide-y-transition>
  </v-container>
</template>


<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component({})
export default class SimpleSample extends Vue {
  //All the code for your component goes here
  //Data
  private name = 'Your Name Here'
  private books = ['The Martian', 'War of the Spark']

  //Computed
  get lengthOfName() {
    return this.name.length
  }
}
</script>
