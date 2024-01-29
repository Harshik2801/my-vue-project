<!-- WorkingArea.vue -->
<template>
  <div class="working-area" style="background-color: #F0CFBA; color: #464646; padding: 20px; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; flex: 1;">
    <component :is="activeComponent" />
  </div>
</template>

<script>
import CreateForm from './createAcc.vue';
import SearchCompanyForm from './SearchCompanyForm.vue';


export default {
  props: {
    activeComponent: String,
  },
  components: {
    CreateForm,
    SearchCompanyForm
    // ... other components ...
  },
};
</script>
