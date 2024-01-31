<template>
    <div id="right-panel">
      <h2>Package List</h2>
  
      <!-- Search Bar -->
      <label class="lbl" for="text">Search Packages</label>
      <br>
      <input class="search-input" type="text" v-model="searchTerm" @input="filterData" placeholder="Search by name, country, price, minutes">
      <!-- Table -->
      <table class="table-container" v-if="filteredPackages.length > 0">
        <thead>
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Country</th>
            <th>Price</th>
            <th>Minutes</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="paCkage in filteredPackages" :key="paCkage.id">
            <td>{{ paCkage.id }}</td>
            <td>{{ paCkage.name }}</td>
            <td>{{ paCkage.country }}</td>
            <td>{{ paCkage.price }}</td>
            <td>{{ paCkage.minutes }}</td>
          </tr>
        </tbody>
      </table>
      <div v-else>
        <p>Loading minute packages...</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'RightPanel',
    data() {
      return {
        minutePackages: [],
        searchTerm: ''
      };
    },
    computed: {
      filteredPackages() {
        // Filter the minute packages based on the search term
        const searchTerm = this.searchTerm.toLowerCase();
        return this.minutePackages.filter(paCkage =>
          paCkage.id.toLowerCase().includes(searchTerm) ||
          paCkage.name.toLowerCase().includes(searchTerm) ||
          paCkage.country.toLowerCase().includes(searchTerm) ||
          paCkage.price.toString().includes(searchTerm) ||
          paCkage.minutes.toString().includes(searchTerm)
        );
      }
    },
    mounted() {
      this.fetchMinutePackages();
    },
    methods: {
      async fetchMinutePackages() {
        try {
          const response = await fetch('http://localhost:3000/MinutePackage');
          const data = await response.json();
          this.minutePackages = data;
        } catch (error) {
          console.error('Error fetching minute packages:', error);
        }
      },
      filterData() {
        // Update the filtered data when the search term changes
        // This is handled automatically by the computed property
      }
    }
  };
  </script>
  
  <style scoped>
  *{
    font-family: 'Poppins', sans-serif;
  }
    #right-panel {
        float: left;
  width: 65%; /* Adjust the width as needed */
  box-sizing: border-box;
  padding: 40px;
  background: rgba(27, 27, 27, 0.55);
  min-height: 10vh;
  margin : 30px;
  color: wheat;
  border-style: solid;
  border-radius: 7px;

  }

  h2{
    padding: 5px;
    margin-top: -28px;
    font-size: 30px;
    align-items: center;
  }

    /* Search input styles */
    .search-input {
      width: 300px;
      padding: 10px;
      border: 2px solid #ccc;
      border-radius: 5px;
      margin-top:5px;
      margin-bottom:15px;
      outline: none;
      font-size: 16px;
    }
    .lbl{
        font-size: 15px;
    }

    .table-container {
      margin-top: 20px;
    }

    /* Table styles */
    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 20px;
      font-size: 16px;
      border-radius: 5px;
      overflow: hidden;
      box-shadow: 0 0 20px rgba(0, 0, 0, 0.7);
    }

    /* Table header styles */
    th, td {
      padding: 15px;
      font-weight: 500;
      text-align: left;
      border-bottom: 1px solid #ddd;
    }

    th {
      background-color: #36393c;
      color: #fff;
    }

    /* Alternating row colors */
    tr:nth-child(odd) {
      background-color: #231313;
    }
    tr:nth-child(even) {
      background-color: #504c4c;
    }
  </style>