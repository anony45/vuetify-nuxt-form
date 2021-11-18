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
              <p class="a">Sign-up for Membership Here</p> <br>
              <p class="b">Please complete the form below to join Coast People's Forum. Once you register, 
              your membership will be approved by the admin and you will be able to access our Members Portal</p>
              </v-col>
              </v-row>
       </v-banner>
         </div><br>
         <v-row  justify='center'>
      <v-col cols='10' lg='7' sm="12" md="8">
       <v-form ref="form" >
        <v-row  justify='center'>
         <v-col >
          <v-col cols="12" sm="8">
            <v-text-field v-model="names" label="Name" required outlined dense color="orange" :rules="nameRules">
             </v-text-field>
             <v-text-field v-model="email" label="Email" :rules="emailRules"  required outlined dense  color="orange">
             </v-text-field>
             <v-row >
              <v-col cols="12" sm="5" lg="3">
                <v-select label='Country Code'  v-model="country" :items="itemList" item-text="name" item-value="country-code" required outlined dense color="orange"></v-select>
              </v-col>
              <v-col cols="12" sm="7" lg="9">
               <v-text-field v-model="phonenumber" label="Phone number" :rules="phoneRules" required outlined dense color="orange">
               </v-text-field>
              </v-col>
             </v-row>
             <v-text-field v-model="profession" label="Profession" required outlined dense color="orange">
             </v-text-field>
             <v-select v-model="gender" label="Gender" required outlined dense color="orange" :items="items">
             </v-select>
             <v-select v-model="county" label="County" required outlined dense color="orange" :items="counties">
            </v-select>
             <v-text-field v-model="password" label="Password" :rules="passwordRules" type="password" required outlined dense color="orange">
             </v-text-field>
             <v-text-field v-model="confirmpassword" label="Confirm Password" type="password" :rules="[(password === confirmpassword) || 'Password must match',v => !!v || 'Password is required']" required outlined dense color="orange">
              </v-text-field>
              <v-btn color="orange" @click="submitForm"> REGISTER </v-btn>          
          </v-col>
       </v-col>
    </v-row>  
    </v-form> 
    </v-col>
    </v-row><br>
         <myfooter></myfooter>
  </v-app>
</template>

<script>
import axios from 'axios'
  export default {

    data: () => ({
      countries:"",
      country:"Kenya",
      itemList: [],
      phone:"",
      names:"test alumnipad",
      email:"",
      phonenumber:"",
      profession:"",
      gender:"",
      county:"",
      password:"",
      confirmpassword:"",
       nameRules: [
      v => !!v || 'name is required',
      ],
      emailRules: [
      v => !!v || 'E-mail is required',
      v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
      passwordRules: [
      v => !!v || 'Password is required',
      v => (v && v.length >= 8) || 'Password must be 8  characters or more!',
      ],
       phoneRules: [
      v => !!v || 'Phone is required',
      ],
      items:['male','female'],
      counties:['Nairobi','Mombasa','Kwale','kilifi','Tana River','Taita Taveta','Garissa','Wajir','Mandera','Marsabit','Isiolo','Kitui','Machakos','Makueni','Nyandarua','Nyeri','Kirinyaga','Muranga','Lamu','Tharaka nithi','Kiambu','Turkana','West Pokot','Samburu','Transzoia','Uasin Gishu','Elgeyo Marakwet','Nandi','Baringo','Laikipia','Meru','Embu','Kisumu','Kajiado','Kericho','nakuru','narok','vihiga'],
    }),
    mounted () {
    this.getList()
  },
  methods: {
    getList :function () {
      axios.get('https://app.alumnipad.com/api/countries').then( response => {
        this.itemList = Object.values(response.data).sort((a,b) => {
          return a.name.localeCompare(b.name)
        })
        
           })
    },
    submitForm () {
    this.$refs.form.validate();
    }, 
    newList (){
      this.itemList.forEach(function(item,i){
        if(item.name === "kenya"){
          itemList.splice(i, 1);
           itemList.unshift(item);
        }
        });
     console.log(data);
      }
    }
  } 
  

</script>
<style>
p{
 
  word-break: keep-all;
  font-family:calibri light;
  width:650px;
  font:100;



}
p.a{
  font-size:39px;
  word-break: keep-all;
  margin-top:125px;

  
}
p.b{
font-size:23px;
font-weight:lighter;
padding-left:auto;
word-spacing:4px;
line-height:30px;

}

</style>

