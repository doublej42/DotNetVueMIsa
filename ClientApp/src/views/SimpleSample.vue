<template>
  <v-container fluid>
    <!-- always have one tag at the top level -->
    <v-slide-y-transition mode="out-in">
      <v-row>
        <v-col>
          <simple-component subtitle="This is Defined in the component above" />
          <simple-component subtitle="This is a second copy" />
        </v-col>
      </v-row>
    </v-slide-y-transition>
  </v-container>
</template>


<script lang="ts">
import { Component, Vue} from 'vue-property-decorator'
import SimpleComponent from '../components/SimpleComponent.vue'
@Component({
  components: { SimpleComponent }
})
export default class SimpleSample extends Vue {}
</script>
