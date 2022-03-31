<template>
  <div class="vacancy box">
    <h1 class="job-title">{{ vacancy.title }}</h1>
    <div class="block"></div>
    <span>{{ vacancy.company }}</span>
    <p>{{ vacancy.city }}</p>
    <div class="block"></div>
    <p>{{ vacancy.description }}</p>
    <div class="is-flex is-justify-content-space-between">
      <button @click="handleApply(vacancy)" class="button is-success mt-2">
        Apply
      </button>
      <button @click="handleDelete(vacancy)" class="button is-danger mt-2">
        Delete
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "VacancyComponent",
  data() {
    return {};
  },
  props: {
    vacancy: {
      type: Object,
      required: true,
    },
  },
  methods: {
    handleApply(vacancy) {
      window.alert(`Applied job for ${vacancy.title}`);
    },
    handleDelete(vacancy) {
      this.$emit("delete", vacancy);
    },
  },
};
</script>

<style scoped>
.vacancy {
  margin: 15px 0;
}
.job-title {
  font-size: 22px;
  font-weight: bold;
}
span {
  font-weight: bold;
  margin-bottom: 5px;
  text-transform: uppercase;
}
</style>
