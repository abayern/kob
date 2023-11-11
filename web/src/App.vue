<template>
  <NavBar />
  <router-view />
</template>
 
<script>

import NavBar from '@/components/NavBar.vue'
import "bootstrap/dist/css/bootstrap.min.css"
import "bootstrap/dist/js/bootstrap"
import $ from 'jquery'
export default{
  components:{
    NavBar
  },
  setup(){
    $.ajax({
      url: "http://127.0.0.1:3000/user/account/token/",
      type: "post",
      data:{
        username: 'linyi',
        password: "123",
      },
      success(resp){
        console.log(resp);
      },
      error(resp){
        console.log(resp);
      }
    });
    $.ajax({
      url: "http://127.0.0.1:3000/user/account/info/",
      type: "get",
      headers: {
        Authorization: "Bearer " + "eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJkMzgxNzU1MmZkYTA0ODlhODYyNjZmMGFjNDk3ZGJmYSIsInN1YiI6IjEiLCJpc3MiOiJzZyIsImlhdCI6MTY5OTI2OTQ4MiwiZXhwIjoxNzAwNDc5MDgyfQ.1RsPbA-_FdkcuONsLu9EbcXtqkOT0W6vsQo3HvtJp2U"
      },
      success(resp){
        console.log(resp);
      },
      error(resp){
        console.log(resp);
      }
    });
    $.ajax({
      url: "http://127.0.0.1:3000/user/account/register/",
      type: "post",
      data: {
        username: "cellia",
        password: "1234",
        confirmedPassword: "1234",
      },
      success(resp){
        console.log(resp);
      },
      error(resp){
        console.log(resp);
      }
    });
  }
}

</script>

<style>
body{
  background-image: url("@/assets/images/background.png");
  background-size: cover;
}
</style>
