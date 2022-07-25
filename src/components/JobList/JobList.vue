<template>
  <div class="joborder">
    <p class="orderterm">Ordered by {{ order }}</p>

    <transition-group name="list" tag="ul" class="joblist">
      <li v-for="job in orderedJobs" :key="job.id" class="joblist-item">
        <div class="job-location">
          <h2 class="title">{{ job.title }}</h2>
          <h4 class="location">{{ job.location }}</h4>
        </div>
        <p class="salary">{{ job.salary }} BDT</p>
        <p class="job-text">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque soluta quas minus? Dolore quidem assumenda nostrum sunt quia, explicabo vero!
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque soluta quas minus? Dolore quidem assumenda nostrum sunt quia, explicabo vero!
        </p>
      </li>
    </transition-group>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, PropType } from 'vue'
import Job from '@/types/Job';
import OrderTerm from '@/types/OrderTerm';

export default defineComponent({
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>
    },
    order: {
      required: true,
      type: String as PropType<OrderTerm>
    }
  },
  setup(props) {
    const orderedJobs = computed(() => {
      return [...props.jobs].sort((a: Job, b: Job) => {
        return a[props.order] > b[props.order] ? 1 : -1
      })
    });

    return { orderedJobs }
  }
})
</script>