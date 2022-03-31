<template>
  <div>
    <section class="hero is-warning is-small">
      <div class="hero-body">
        <p class="title">Find your dream job here</p>
        <p class="subtitle">Apply for any below vacancies</p>
      </div>
    </section>
    <VacancyForm @save="handleEvent" />
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
import VacancyForm from "../components/VacancyForm.vue";
import { vacancies } from "../../data.js";
export default {
  components: { VacancyForm, Vacancy },
  name: "HomePage",
  data() {
    return {
      vacancies,
    };
  },
  methods: {
    handleEvent(formdata) {
      this.vacancies.unshift(formdata);
    },
    handleDeleteEvent(vacancy) {
      this.vacancies = this.vacancies.filter(
        (newVacancy) => newVacancy.id !== vacancy.id
      );
    },
  },
};
</script>

<style scoped></style>
