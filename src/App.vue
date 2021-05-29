<template>
  <div class="app">
    <header>
      <div class="text-center">
        <button class="btn btn-outline-success m-2" @click="handleCLick('title')">Order by Title</button>
        <button class="btn btn-outline-success m-2" @click="handleCLick('salary')">Order by Salary</button>
        <button class="btn btn-outline-success m-2" @click="handleCLick('location')">Order by location</button>
      </div>
    </header>
    <JobList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import JobList from "./components/JobsList.vue";
import Job from "./types/Job";
import OrderTerm from "./types/OrderTerm";

export default defineComponent({
  name: "App",
  components: { JobList },
  setup() {
    const jobs = ref<Job[]>([
      { title: "Farm worker", location: "Lon lon ranch", salary: 30000, id: "1" },
      { title: "Quarry", location: "Death mountain", salary: 40000, id: "2" },
      { title: "Flute player", location: "Lost woods", salary: 35000, id: "3" },
      { title: "Fisherman", location: "Lake Hylia", salary: 2300, id: "4" },
      { title: "Prision guard", location: "Gerudo valley", salary: 32000, id: "5" },
    ]);

    const order = ref<OrderTerm>("title");

    const handleCLick = (term: OrderTerm) => {
      order.value = term;
    };

    return { jobs, handleCLick, order };
  },
  methods: {},
});
</script>

<style></style>
