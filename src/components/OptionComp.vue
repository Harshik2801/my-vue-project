<!-- Options.vue -->
<template>
  <nav class="options-column" style="background-color: #FEBE98; color: #464646; padding: 1rem; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">
    <ul style="list-style-type: none; padding: 0; margin: 0;">
      <li @click="navigateTo('CreateForm')" class="option" style="cursor: pointer; font-size: 1.2rem;">
        <span style="margin-right: 0.5rem;">🌿</span> Create
      </li>
      <li @click="navigateTo('SearchCompanyForm')" class="option" style="cursor: pointer; font-size: 1.2rem;">
        <span style="margin-right: 0.5rem;">🔍</span> Search Company
      </li>
      <!-- ... other options ... -->
    </ul>
  </nav>
</template>

<script>
export default {
  methods: {
    navigateTo(componentName) {
      this.$emit('navigateTo', componentName);
    },
  },
};
</script>

<style scoped>
.options-column {
  box-shadow: 2px 0px 8px rgba(0, 0, 0, 0.2); /* Add shadow to the left */
  width: 20%; /* Set default width to 20% */
}

.option {
  padding: 0.5rem;
  margin-bottom: 0.5rem;
  background-color: #FEBE98;
  border-radius: 4px;
  transition: background-color 0.3s;
  cursor: pointer;
}

.option:hover {
  background-color: #F0CFBA;
}

/* Media query for larger devices */
@media screen and (min-width: 768px) {
  .options-column {
    width: 20%; /* Adjust width for larger devices */
  }
}
</style>
