<!-- App.vue -->
<template>
  <div style="height: 100vh; display: flex; flex-direction: column;">
    <Navbar @navigateTo="navigateTo" />
    <div style="display: flex; flex: 1;">
      <Options @navigateTo="navigateTo" />
      <WorkingArea :activeComponent="activeComponent" />
    </div>
  </div>
  <SearchForm v-if="showForm" @submit="handleFormSubmit" />
  <SearchResults v-else @goBack="handleGoBack" :searchData="searchData" />
</template>

<script>
import Navbar from './components/NavBar.vue';
import Options from './components/OptionComp.vue';
import WorkingArea from './components/WorkingArea.vue';
import SearchForm from "@/components/SearchCompanyForm.vue";
import SearchResults from "@/components/SearchResults.vue";

export default {
  components: {
    Navbar,
    Options,
    WorkingArea,
    SearchForm,
    SearchResults
  },
  data() {
    return {
      activeComponent: null,
      showForm: true,
      searchData: null,
    };
  },
  methods: {
    navigateTo(componentName) {
      this.activeComponent = componentName;
    },
    handleFormSubmit(formData) {
      // Assuming you have a method to perform the search and retrieve results
      this.searchData = this.performSearch(formData); // Replace this with actual search logic

      // Switch to search results component
      this.showForm = false;
    },
    handleGoBack() {
      // Switch back to the search form component
      this.showForm = true;
    },
    // Perform your actual search logic here
    // performSearch(formData) {
    //   // For illustration purposes, return some dummy data
    //   return [
    //     { action: "Action1", siteId: "Site1", type: "Type1", certified: "Yes", watch: "Yes", status: "Active" },
    //     { action: "Action2", siteId: "Site2", type: "Type2", certified: "No", watch: "No", status: "Inactive" },
    //   ];
    // },
  },
};
</script>
