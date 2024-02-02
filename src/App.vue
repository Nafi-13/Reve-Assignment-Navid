<template>
  <div>
  <NavHeader></NavHeader>
  <Container></Container>
</div>
</template>

<script>
import NavHeader from './components/NavHeader.vue';
import Container from './components/Container.vue';

export default {
  name: 'App',
  components: {
    NavHeader,
    Container
  }
}
</script>

<style>
  body{
    margin : 0px;
    padding: 0px;
    box-sizing: border-box;
    background-image: url(Sample.jpg);
}
</style>


