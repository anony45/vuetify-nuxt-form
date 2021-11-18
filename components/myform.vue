<template>
    <v-app>
        <v-row  justify='center'>
          <v-col cols='10' lg='7' sm="12" md="8">
            <v-form ref="form" >
              <v-row  justify='center'>
            <v-col>
             <v-col cols="12" sm="8">
             <v-text-field v-model="names" label="Name" required outlined dense color="orange" :rules="nameRules">
             </v-text-field>
             <v-text-field v-model="email" label="Email" :rules="emailRules"  required outlined dense  color="orange">
             </v-text-field>
             <v-row >
              <v-col cols="12" sm="5" lg="3">
                <v-select label='Country Code'  v-model="country" :items="countryCodes" item-text="name" item-value="country-code" required outlined dense color="orange"></v-select>
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
    <v-simple-table>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">
            Name
          </th>
          <th class="text-left">
            Email
          </th>
          <th class="text-left">
            country code
          </th>
          <th class="text-left">
            Phone Number
          </th>
          <th class="text-left">
            profession
          </th>
          <th class="text-left">
            gender
          </th>
          <th class="text-left">
            County
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(entry, index) in tableData" :key="index">
          <td>{{ entry.names }}</td>
          <td>{{ entry.email }}</td>
          <td>{{ entry.country }}</td>
          <td>{{ entry.phonenumber }}</td>
          <td>{{ entry.profession }}</td>
          <td>{{ entry.gender }}</td>
          <td>{{ entry.county }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
    
  
    </v-col>
    </v-row><br>
    
    </v-app>
</template>
<script>
import axios from 'axios'
  export default {

    data: () => ({
      country:"Kenya",
      countryCodes: [],
      phone:"",
      names:"",
      email:"",
      phonenumber:"",
      profession:"",
      gender:"",
      county:"",
      password:"",
      confirmpassword:"",
      tableData: [],
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
    this.getCountries();
     },
    methods: {
    getCountries :function () {
      var firstCountry="Kenya";
      axios.get('https://app.alumnipad.com/api/countries').then( response => {
        this.countryCodes= Object.values(response.data);
        this.countryCodes.sort((a,b) => {
          return a.name.localeCompare(b.name)
        })
        this.countryCodes.sort((x,y) => {
          return x.name === firstCountry ? -1 : y.name === firstCountry ? 1:0   });
          
        });
    },
    submitForm () {
    this.$refs.form.validate();

    this.tableData.push({ names: this.names, email:this.email,
    country:this.country, phonenumber:this.phonenumber, profession: this.profession,
    gender:this.gender, county:this.county
    });
    }, 
    },
  } 
  

</script>
<style>

</style>
