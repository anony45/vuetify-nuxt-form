<template>
  <v-app dark>
  <div id="header1">
  <v-system-bar class="orange white--text" app >COAST PEOPLE'S FORUM</v-system-bar><br>
    <br>
     <v-app-bar app color="white" height="100">
       <v-img class="mx-2" src="logo.png" max-height="100" max-width="150"></v-img>
        <v-spacer></v-spacer>
          <v-btn text outlined color="orange">LOGIN</v-btn>

       </v-app-bar>

          <br>
          <div id="header2">
          <v-app-bar class="orange white--text" height="310">  <v-toolbar-title ><p class="a"> Sign-up for Membership Here</p> <br/> 
          <p class="b" >Please complete the form below to join Coast People's Forum.<br> Once you register, your membership will be approved by the <br> admin and you will be able to access our Members Portal</p>
          </v-toolbar-title>      
         </v-app-bar></div>
         </div>
         <myform></myform>
         <myfooter></myfooter>
    
  </v-app>
</template>

<script>
export default {
  data () {
    return {
    }
  }
}
</script>
<style>
p{
  width:600px;
  word-break: keep-all;
  margin-left :300px;
  padding-right:200px;
  text-align:center;
  font-weight:normal;


}
p.a{
  text-align:center;
  font-size:35px;
  word-break: keep-all;
  font-family:sans-serif;
  margin-top:75px;

  
}
p.b{
font-family:sans-serif;
font-size:21px;
margin-top:-30px;
font-weight:normal;
}

</style>

