<template>
  <v-app>
  <div id="header1">
  <v-system-bar class="orange white--text" app >COAST PEOPLE'S FORUM</v-system-bar><br>
    <br>
     <v-app-bar app color="white" height="100">
       <v-img class="mx-2" src="logo.png" max-height="100" max-width="150"></v-img>
        <v-spacer></v-spacer>
          <v-btn text outlined color="orange">LOGIN</v-btn>

       </v-app-bar>
          <div id="header2">
          <v-card height="350" class="orange white--text" sm="8">
          <v-card-text class="orange white--text font-weight-light">
          <p class="a">Sign-up for Membership Here</p>
          <p class="b">Please complete the form below to join Coast People's Forum. Once you register, your membership will be approved by the admin and you will be able to access our Members Portal</p>
          </v-card-text>
          
          </v-card>
     </div>
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
 
  word-break: keep-all;
  margin-left :350px;
  padding-right:200px;
  font-weight:lighter;
  font-family:calibri light;
  width:650px;
  padding: 10px;
  font:100;




}
p.a{
  font-size:35px;
  word-break: keep-all;
  margin-top:100px;

  
}
p.b{
font-size:23px;
font-weight:lighter;
padding-left:auto;
word-spacing:4px;
line-height:30px;
}

</style>

