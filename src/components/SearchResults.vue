<!-- SearchResults.vue -->
<template>
  <div>
    <h2>Search Results</h2>
    <!-- Display company details and search results -->
    <div class="company-details">
      <!-- Display company details from form data -->
      <p><strong>Company Name:</strong> {{ searchData.companyName }}</p>
      <p><strong>Company Code:</strong> {{ searchData.companyCode }}</p>
      <p><strong>Company Number:</strong> {{ searchData.companyNumber }}</p>
      <p><strong>Legal Entity ID:</strong> {{ searchData.legalEntityId }}</p>
    </div>

    <!-- Table with search results -->
    <table>
      <thead>
        <tr>
          <th>Action</th>
          <th>Site ID</th>
          <th>Type</th>
          <th>Certified</th>
          <th>Watch</th>
          <th>Status</th>
        </tr>
      </thead>
      <tbody>
        <!-- Render search results dynamically -->
        <tr v-for="(result, index) in searchData.results" :key="index">
          <td>{{ result.action }}</td>
          <td>{{ result.siteId }}</td>
          <td>{{ result.type }}</td>
          <td>{{ result.certified }}</td>
          <td>{{ result.watch }}</td>
          <td>{{ result.status }}</td>
        </tr>
      </tbody>
    </table>

    <!-- Button to go back to the search form -->
    <button @click="goBack">Go Back</button>
  </div>
</template>

<script>
export default {
  props: {
    searchData: Object,
  },
  methods: {
    goBack() {
      // Emit the goBack event to the parent
      this.$emit("goBack");
    },
  },
};
</script>