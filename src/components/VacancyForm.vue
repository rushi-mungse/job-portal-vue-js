<template>
  <div>
    <div class="create-vac box">
      <p>Create Vacancies</p>

      <form @submit.prevent="handleFormData">
        <input
          v-model="form.title"
          class="input"
          type="text"
          placeholder="Job title"
        />
        <input
          v-model="form.company"
          class="input"
          type="text"
          placeholder="Company name"
        />
        <input
          v-model="form.city"
          class="input"
          type="text"
          placeholder="City name"
        />
        <textarea
          class="input"
          type="text"
          placeholder="Description"
          v-model="form.description"
        ></textarea>
        <button class="button is-success">Create</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "VacancyFormComponent",
  data() {
    return {
      form: { title: "", company: "", city: "", description: "" },
    };
  },
  methods: {
    handleFormData() {
      this.$emit("save", { ...this.form, id: new Date().getTime.toString() });
      for (let key in this.form) {
        this.form[key] = "";
      }
    },
  },
};
</script>

<style scoped>
.create-vac {
  margin-top: 20px;
}
.create-vac p {
  font-size: 20px;
  color: rgb(255, 145, 0);
}
input,
textarea,
button {
  margin-top: 10px;
  background-color: rgb(148, 216, 168);
  color: black;
  outline: none;
  border: none;
}
input::placeholder,
textarea::placeholder {
  color: rgb(117, 109, 109);
}
</style>
