<template>
  <HeaderNavbar/>
  <RouterView/>
  
</template>

<script>
import HeaderNavbar from "./components/HeaderNavbar";
export default {
  name: 'App',
  components:{
    HeaderNavbar,
  }
  
}
</script>

