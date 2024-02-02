<template>
  <header>
    <nav data-aos="fade-down"
    data-aos-delay="50"
    data-aos-duration="800">
      <div class="logo">
        <h4>Buy Minutes</h4>
      </div>
      <ul class="nav-links">
        <li><a href="#">Home</a></li>
        <li><a href="#">Settings</a></li>
        <li><a href="#">Profile Tabs</a></li>
      </ul>
      <div class="burger">
        <div class="line1"></div>
        <div class="line2"></div>
        <div class="line3"></div>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'NavHeader'
};
</script>


<style scoped>
nav{
    display: flex;
    justify-content: space-around;
    align-items: center;
    min-height: 12vh;
    background: rgba(0, 0, 0, 0.65);
    font-family: 'Poppins', sans-serif;
    border-bottom-style: solid;
    border-bottom-color: rgb(249, 225, 118);
    border-bottom-width: 4px;
}

.logo:hover {
  cursor: pointer;
}

.logo{
    color: rgb(247, 194, 114);
    text-transform: uppercase;
    letter-spacing: 3px;
    font-size: 25px;
}

.nav-links{
    display: flex;
    width: 48%;
    justify-content: space-around;
}
.nav-links li{
    list-style: none;
}

.nav-links a{
    color: wheat;
    text-decoration: none;
    letter-spacing: 3px;
    font-weight: 500;
    padding: 7px;
    font-size: 21px;
}

a:hover {
      border-style: solid;
      border-color: wheat;
      border-radius : 6px;
      border-width: 2px;
      
    }

.burger{
  display: none;
}

.burger div{
  width: 28px;
  height: 3px;
  background-color: wheat;
  margin: 5px;
}

@media screen and (max-width: 768px){
  nav{
    height: 45vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
  }

  .nav-links{
    display: flex;
    flex-direction: column;
    height: 45%;
  }

  .logo{
    height: 30%;
    font-size: 35px;
  }
  .nav-links li{
    margin-right:50px;
    text-align: center;
}

}
</style>