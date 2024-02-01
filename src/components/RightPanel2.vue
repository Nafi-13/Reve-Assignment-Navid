<template>
    <div id="right-panel-2">
      <h1>Account Information</h1>
      <h3>Username - Md. Navid Razzaque</h3>
      <h3>Current Package - Turbo </h3>
    </div>
  </template>

<style scoped>

*{
  font-family: 'Poppins', sans-serif;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

#right-panel-2 {
  float: left;
  width: 60%; /* Adjust the width as needed */
  box-sizing: border-box;
  padding: 10px;
  background: rgba(27, 27, 27, 0.55);
  border-radius: 10px;
  margin : 30px;
  min-height : 30vh;
  border-style: solid;
  border-color: wheat;
  color: wheat;
}

h1{
  margin-top: 20px;
  margin-left : 10px;
  padding: 5px;
  font-size: 30px;
  align-items: left;
  color: rgb(247, 194, 114);
}

h3{
  margin-top: 20px;
  margin-left : 10px;
  padding: 5px;
  font-size: 20px;
  align-items: left;
}

@media screen and (max-width: 768px){
  #right-panel-2{
    width: 90%;
  }

  h1{
    text-align: center;
  }
}

</style>