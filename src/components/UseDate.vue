<template>
  <div class="use-date">
    <h1>Use Date Picker</h1>
    <div class="form-group">
      <label for="day">Day:</label>
      <input type="number" id="day" v-model="day" min="1" max="31" />
    </div>
    <div class="form-group">
      <label for="month">Month:</label>
      <input type="number" id="month" v-model="month" min="1" max="12" />
    </div>
    <div class="form-group">
      <label for="year">Year:</label>
      <input type="number" id="year" v-model="year" />
    </div>
    <p>Selected Date: {{ selectedDtae }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      day: 1,
      month: 1,
      year: 2023,
    };
  },
  computed: {
    selectedDate() {
      const formattedDay = this.day.toString().padStart(2, '0');
      const formattedMonth = this.month.toString().padStart(2, '0');
      return `${formattedDay}-${formattedMonth}-${this.year}`;
    },
  },
};
</script>

<style scoped>
.use-date {
  max-width: 400px;
  margin: auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
}

.form-group {
  margin-bottom: 15px;
}

label {
  display: block;
  margin-bottom: 5px;
}

input {
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
}
</style>
