<template>
  <div id="app">
    <p>Name is: {{ name }} and Age is: {{ age }}</p>
    <button @click="changeName('Istiak')" class="btn-change" type="button">Change Name</button>
    <button @click="changeAge(30)" class="btn-change" type="button">Change Age</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

type numberOrString = number | string

export default defineComponent({
  name: 'App',
  components: {
    
  },
  data() {
    return {
      name: 'Tushar' as string,
      age: 29 as numberOrString
    }
  },
  methods: {
    changeName(name: string) {
      this.name = name
    },
    changeAge(age: numberOrString) {
      this.age = age
    }
  }
});
</script>

<style lang="scss">

</style>
