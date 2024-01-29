
<template>
    <h2>Search Company</h2>
    <div class="search-company-form">
      <div class="form-box">
        <div class="form-content">
          <!-- First column -->
          
          <div class="form-column">
            <div class="form-group">
              <label for="companyName">Company Name:</label>
              <input type="text" id="companyName" v-model="formData.companyName" class="input-field" />
            </div>
            <div class="form-group">
              <label for="companyId">Company ID:</label>
              <input type="text" id="companyId" v-model="formData.companyId" class="input-field" />
            </div>
            <div class="form-group">
              <label for="companyCode">Company Code:</label>
              <input type="text" id="companyCode" v-model="formData.companyCode" class="input-field" />
            </div>
            <div class="form-group">
              <label for="status">Status:</label>
              <select id="status" v-model="formData.status" class="input-field">
                <option value="active">Active</option>
                <option value="passive">Passive</option>
              </select>
            </div>
          </div>
          <div class="column-gap"></div>
          <!-- Second column -->
          <div class="form-column">
            <div class="form-group">
              <label for="legalEntityId">Legal Entity ID:</label>
              <input type="text" id="legalEntityId" v-model="formData.legalEntityId" class="input-field" />
            </div>
            <div class="form-group">
              <label for="companyGroup">Company Group:</label>
              <input type="text" id="companyGroup" v-model="formData.companyGroup" class="input-field" />
            </div>
            <div class="form-group">
              <label for="partnership">Partnership:</label>
              <input type="text" id="partnership" v-model="formData.partnership" class="input-field" />
            </div>
            <div class="form-group">
              <label for="brandName">Brand Name:</label>
              <input type="text" id="brandName" v-model="formData.brandName" class="input-field" />
            </div>
          </div>
        </div>
        <div class="form-actions">
          <button @click="submitForm" class="submit-button">Submit</button>
          <button @click="clearForm" class="clear-button">Clear</button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        formData: {
          companyName: '',
          companyId: '',
          companyCode: '',
          status: 'active',
          legalEntityId: '',
          companyGroup: '',
          partnership: '',
          brandName: '',
        },
      };
    },
    
    methods: {
      
      submitForm() {
        const searchResults = this.performSearch(); 
        this.$router.push({
          name: 'search-results',
          params: {
            companyName: this.formData.companyName,
            companyCode: this.formData.companyCode,
            companyNumber: this.formData.companyNumber,
            legalEntityId: this.formData.legalEntityId,
            searchResults: searchResults,
          },
        });
      },
      
      clearForm() {
        // Clear form entries
        this.formData = {
          companyName: '',
          companyId: '',
          companyCode: '',
          status: 'active',
          legalEntityId: '',
          companyGroup: '',
          partnership: '',
          brandName: '',
        };
      },
    },
  };
  </script>
  
  <style scoped>
/* Styles for the Search Company Form component */
.search-company-form {
  background-color: #F87472;
  padding: 1rem;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  border: 2px double #464646; /* Double border */
}

.form-content {
  display: flex;
  justify-content: space-between;
  
}

.form-column {
  flex: 1;
}

.column-gap {
  width: 4rem; /* Adjust the gap width as needed */
}

.form-group {
  margin-bottom: 1.5rem;
}

.input-field,
.text-area,
select {
  width: 100%;
  padding: 0.5rem;
  box-sizing: border-box;
  background-color: #F0CFBA;
  border: 1px solid #464646;
  border-radius: 4px;
}

.form-actions {
  display: flex;
  justify-content: space-between;
  margin-top: 1rem;
}

.submit-button{
    background-color: #FEBE98;
    color:#464646;
    padding: 0.7rem 1rem;
    cursor: pointer;
    border: none;
    border-radius: 4px;
    font-size: 1rem;
    transition: background-color 0.3s;
    flex: 1;
    margin-right: 4rem;
}
.clear-button {
  flex: 1; /* Occupy equal space */
  background-color:  #F0CFBA;
  color: #464646;
  padding: 0.7rem 1rem;
  cursor: pointer;
  border: none;
  border-radius: 4px;
  font-size: 1rem;
  transition: background-color 0.3s;
}

.submit-button:hover {
  background-color: #F0CFBA;
  color: #464646;
  
}
.input-field {
  height: 2rem; /* Adjust the height as needed */
  width: calc(100% - 0.6rem); /* Decreased width */
  font-family: 'Comic Sans MS', cursive, sans-serif;  /* Adjust the height as needed */
}
.clear-button:hover {
  background-color: #FFF;
  color: #464646;
}
</style>