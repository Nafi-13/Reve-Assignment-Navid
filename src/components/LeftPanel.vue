<template>
    <div id="left-panel">
      <h2>Menu Bar</h2>
      <ul>
        <li @click="showAccountInformation"><a href="#"> Account Information</a></li>
        <li @click="showMinutePackages"><a href="#"> Minute Packages </a></li>
        <!-- Add more menu items as needed -->
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    name: 'LeftPanel',
    methods: {
      showAccountInformation() {
        // Emit an event to notify the parent component (App) about the selected menu item
        this.$emit('update-selected-menu-item', 'account');
      },
      showMinutePackages() {
        // Emit an event to notify the parent component (App) about the selected menu item
        this.$emit('update-selected-menu-item', 'packages');
      }
      // Add more methods for other menu items if needed
    }
  };
  </script>
  
  <style scoped>

  *{
    font-family: 'Poppins', sans-serif;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  #left-panel {
    float: left;
    width: 25%; /* Adjust the width as needed */
    box-sizing: border-box;
    padding: 10px;
    background-color: #f1f1f1;
    border-radius: 10px;
    margin : 30px;
    min-height : 30vh;
    background: transparent;
    border-style: solid;
    border-color: wheat;
    color: wheat;
  }

  h2{
    margin-top: 20px;
    padding: 5px;
    font-size: 30px;
    align-items: center;
  }

  ul{
    align-items: center;
    margin-top : 10px;
    margin-right:35px;
  }

  li{
    list-style: none;
    padding: 10px;
    margin-top : 15px;
    margin-bottom: 15px;
    font-size: 18px;
    
  }
  

  a {
      color: wheat; /* Default text color */
      background-color: transparent; /* Default background color */
      text-decoration: none; /* Remove underline */
      transition: background-color 0.2s, color 0.2s, scale 0.2s; /* Smooth transition for color and background change */
      padding: 10px 20px; /* Add padding for better readability */
      border-radius: 5px;
      border-style: solid;
      border-color: wheat;
      font-weight: 400;    
    }

    /* Hover state styles */
    a:hover {
      color: rgb(13, 13, 13); /* Change text color on hover to provide contrast */
      background-color: wheat; /* Change background color on hover */
      scale: 1.1;
    }
  </style>