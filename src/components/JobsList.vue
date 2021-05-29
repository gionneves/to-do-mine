<template>
  <link
    rel="stylesheet"
    href="https://use.fontawesome.com/releases/v5.1.1/css/all.css"
    integrity="sha384-O8whS3fhG2OnA5Kas0Y9l3cfpmYjapjI0E4theH4iuMD+pLhbf6JI0jIMfYcK3yZ"
    crossorigin="anonymous"
  />
  <div class="job-list">
    <div class="container">
      <ul>
        <p>Ordered by {{ order }}</p>
        <li class="container border shadow m-3" v-for="job in jobs" :key="job.id">
          <h2>{{ job.title }} in {{ job.location }}</h2>
          <div class="salary text-success">
            <p><i class="fas fa-money-bill-wave"></i> {{ job.salary }} Ruppes</p>
          </div>
          <div class="description">
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Animi voluptates suscipit quidem omnis! Magnam
              autem laudantium animi, deleniti eos minima facere voluptate labore nostrum quae eligendi exercitationem.
              Debitis, nostrum necessitatibus!
            </p>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import Job from "@/types/Job";
import OrderTerm from "@/types/OrderTerm";

export default defineComponent({
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>,
    },
    order: {
      required: true,
      type: String as PropType<OrderTerm>,
    },
  },
});
</script>
