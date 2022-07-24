<template>
  <div class="d-none">
    <p>Name is: {{ name }} and Age is: {{ age }}</p>
    <button @click="changeName('Istiak')" class="btn-change" type="button">Change Name</button>
    <button @click="changeAge(30)" class="btn-change" type="button">Change Age</button>
  </div>

  <p>{{ jobs[0].location }}</p>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue';
import Job from './types/Job';

// type numberOrString = number | string

export default defineComponent({
  name: 'App',
  components: {},
  setup() {
    // const state = reactive({
    //   name: 'Tushar' as string,
    //   age: 29 as numberOrString
    // })

    // return { ...toRefs(state) }
  
    // const name = ref<string>('Tushar')
    // const age = ref<numberOrString>(29)

    // return { name, age }
  
    const jobs = ref<Job[]>([
      { title: 'farm worker', location: 'lon lon ranch', salary: 30000, id: '1' },
      { title: 'quarryman', location: 'death mountain', salary: 40000, id: '2' },
      { title: 'flute player', location: 'the lost woods', salary: 35000, id: '3' },
      { title: 'fisherman', location: 'lake hylia', salary: 21000, id: '4' },
      { title: 'prison guard', location: 'gerudo valley', salary: 32000, id: '5' }
    ])

    return { jobs }
  },
  methods: {
    // changeName(name: string) {
    //   this.name = name
    //   return name
    // },
    // changeAge(age: numberOrString) {
    //   this.age = age
    //   return age
    // }
  }
});
</script>

<style lang="scss">

</style>
