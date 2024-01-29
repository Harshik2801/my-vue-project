<!-- CreateForm.vue -->
<template>
  <div>
    <h2 style="margin-bottom: 1rem;">Create Form</h2>
    <div class="form-box">
      <div class="form-content">
        <div class="form-group">
          <label for="name">Name:</label>
          <input type="text" id="name" v-model="formData.name" class="input-field" />
        </div>
        <div class="form-group">
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="formData.email" class="input-field" />
        </div>
        <div class="form-group">
          <label for="message">Message:</label>
          <textarea id="message" v-model="formData.message" class="text-area"></textarea>
        </div>
      </div>
      <button @click="submitForm" class="submit-button">Submit</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      formData: {
        name: '',
        email: '',
        message: '',
      },
    };
  },
  methods: {
    submitForm() {
      // Handle form submission logic
    },
  },
};
</script>

<style scoped>
.form-box {
  background-color: #F87472;
  padding: 1rem;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  border: 2px double #464646; /* Double border */
}

.form-content {
  margin-bottom: 1rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

.input-field,
.text-area {
  width: 100%;
  padding: 0.5rem;
  box-sizing: border-box;
  background-color: #F0CFBA;
  border: 1px solid #464646;
  border-radius: 4px;
}

.submit-button {
  background-color: #FEBE98; /* Changed button color */
  color: #464646;
  padding: 0.7rem 1.5rem;
  cursor: pointer;
  border: none;
  border-radius: 4px;
  font-size: 1rem;
  transition: background-color 0.3s;
}

.submit-button:hover {
  background-color: #F0CFBA;
}
</style>
