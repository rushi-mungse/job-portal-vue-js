<template>
  <div>
    <Vacancy
      v-for="vacancy in vacancies"
      :key="vacancy.id"
      :vacancy="vacancy"
      @delete="handleDeleteEvent"
    />
  </div>
</template>

<script>
import Vacancy from "../components/Vacancy.vue";
import { vacancies } from "../../data.js";
export default {
  name: "VacanciesPage",
  components: { Vacancy },
  data() {
    return {
      vacancies,
    };
  },
  methods: {
    handleDeleteEvent(vacancy) {
      this.vacancies = this.vacancies.filter(
        (newVacancy) => newVacancy.id !== vacancy.id
      );
    },
  },
};
</script>

<style lang="scss" scoped></style>
