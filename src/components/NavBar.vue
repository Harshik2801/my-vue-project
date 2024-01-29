<!-- Navbar.vue -->
<template>
  <div style="background-color: #F87472; color: #464646; padding: 0.5rem; display: flex; align-items: center; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; box-shadow: 0px 2px 8px rgba(0, 0, 0, 0.2);">
    <!-- Refresh icon -->
    <span style="cursor: pointer; margin-right: 1rem;" @click="refreshPage">&#x21BB;</span>
    <!-- Title -->
    <div style="font-size: 1.5rem;">Interactive SPA</div>
  </div>
</template>

<script>
export default {
  methods: {
    refreshPage() {
      // Implement refresh logic
    },
  },
};
</script>
