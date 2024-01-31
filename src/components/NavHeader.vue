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
        <li><a href="#">Profile tabs</a></li>
      </ul>
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

nav:hover {
  cursor: pointer;
}

.logo{
    color: wheat;
    text-transform: uppercase;
    letter-spacing: 3px;
    font-size: 25px;
}

.nav-links{
    display: flex;
    width: 30%;
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

</style>