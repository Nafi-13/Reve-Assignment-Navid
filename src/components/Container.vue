<script>
import { ref } from 'vue';
import RightPanel from './RightPanel.vue';
import RightPanel2 from './RightPanel2.vue';

export default {
  name: 'App',
  components: {
    RightPanel,
    RightPanel2
  },
  setup() {
    const showLeft = ref(true);
    const isInitial = ref(true);

    const toggleLeftPanel = (newVal) => {
      showLeft.value = newVal;
      if(isInitial.value)
      {
        isInitial.value = false;
      }
    };

    const toggleInitial = (newVal) => {
      isInitial.value = newVal;
    };

    return {
      showLeft,
      toggleLeftPanel,
      toggleInitial,
      isInitial
    };
  }
};
</script>

<template>
    <div class="container">
    <div id="left-panel">
      <h2>Menu Bar</h2>
      <ul>
        <li @click="toggleLeftPanel(false)"><a href="#"> Account Information</a></li>
        <li @click="toggleLeftPanel(true)"><a href="#"> Minute Packages </a></li>
      </ul>
    </div>
    <div v-if="isInitial" class="instruction">
        <div class="initial">Select a menu item to get started</div> 
    </div>
    <div v-else>
        <RightPanel v-if="showLeft" data-aos="fade-right"></RightPanel>
        <RightPanel2 v-else data-aos="fade-right"></RightPanel2>
    </div>
</div>
</template>

<style scoped>

  *{
    font-family: 'Poppins', sans-serif;
    
  }

  

  #left-panel {
    float: left;
    
    width: 30%; 
    box-sizing: border-box;
    padding: 10px;
    background: rgba(16, 11, 11, 0.35);
    border-radius: 10px;
    margin : 30px;
    min-height : 30vh;
    border-style: solid;
    border-color: wheat;
    color: wheat;
    display: flex;
    flex-direction: column;
  }

  h2{
    margin-top: 20px;
    padding: 5px;
    font-size: 30px;
    text-align: center;
    color:rgb(247, 194, 114);
  }

  ul{
    align-items: center;
    margin-top : 10px;
    margin-right:35px;
    text-align: center;
  }

  li{
    list-style: none;
    padding: 10px;
    margin-top : 15px;
    margin-bottom: 35px;
    font-size: 18px;
    
  }
  

  a {
      color: wheat;
      background-color: transparent; 
      text-decoration: none; 
      transition: background-color 0.2s, color 0.2s, scale 0.2s; 
      padding: 10px 20px; 
      border-radius: 5px;
      border-style: solid;
      border-color: wheat;
      font-weight: 400;    
    }

    a:hover {
      color: rgb(13, 13, 13); 
      background-color: wheat; 
      scale: 1.1;
    }

    .initial{
    color: whitesmoke;
    font-size: 30px;
    padding: 35px;
    text-align: center;
    font-family: 'Bungee', sans-serif;
    letter-spacing: 2px;
  }

  @media screen and (max-width: 1300px){
    #left-panel{
      width: 40%;
    }
  }

  @media screen and (max-width: 840px){
    .instruction{
      display: none;
    }

    #left-panel{
      width: 90%;
    }

    h2{
      font-size: 35px;
    }

    li{
    padding: 10px;
    margin-top : 15px;
    margin-bottom: 35px;
    font-size: 20px;
  }
  }
  </style>