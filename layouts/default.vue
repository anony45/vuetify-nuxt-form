<template>
  <v-app d-flex>
  <div id="header1">
   <v-system-bar class="orange white--text" app >COAST PEOPLE'S FORUM</v-system-bar><br>
    <br>
     <v-app-bar app color="white" height="80">
       <v-img class="mx-2" src="logo.png" max-height="70" max-width="130"></v-img>
        <v-spacer></v-spacer>
          <v-btn text outlined color="orange">LOGIN</v-btn>
       </v-app-bar>
       <v-banner height="320" class="orange white--text">
           <v-row justify='center'>
              <v-col cols='10' lg='7' sm="12" md="10">
              <p class="mytitle">Sign-up for Membership Here</p> <br>
              <p class="mysubtitle">Please complete the form below to join Coast People's Forum. Once you register, 
              your membership will be approved by the admin and you will be able to access our Members Portal</p>
              </v-col>
              </v-row>
       </v-banner>
         </div><br>
         
          <myform></myform>
         <myfooter></myfooter>
  </v-app>
</template>

<script>


</script>
<style>
p{
 
  word-break: keep-all;
  font-family:calibri light;
  width:650px;
  font:100;



}
.mytitle{
  font-size:39px;
  word-break: keep-all;
  margin-top:125px;

  
}
.mysubtitle{
font-size:23px;
font-weight:lighter;
padding-left:auto;
word-spacing:4px;
line-height:30px;

}

</style>

