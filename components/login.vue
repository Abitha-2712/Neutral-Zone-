<template>
 
    <v-container>
       <v-layout align-center justify-center>
          <v-flex xs12 sm8 md4>
              <v-card class="mx-auto"
                width="400"
                color="white">
                <h3 class="text-h6 text-center " style="padding:5%;">User Login</h3>
                <v-container style="width: 100%;">
              <v-card-text color="black">
                <form ref="form" @submit.prevent="login()">
                    <v-text-field
                         v-model="username"
                         name="username"
                         label="User Name"
                         type="str"
                         placeholder="username"
                         required
                      ></v-text-field>
                       
                       <v-text-field
                         v-model="password"
                         name="password"
                         label="Password"
                         type="password"
                         placeholder="password"
                         required
                      ></v-text-field>
                      
                      <v-card-actions>
                       <v-spacer></v-spacer>
                        <v-row>
                         <v-col> 
                          <v-btn text color="black" block to="/paymentpage">
                            login
                          </v-btn>
                         </v-col>
                          <v-col>
                           <v-btn text color="black" block to="/signup">
                            Register

                            <v-icon icon="mdi-chevron-right" end>
                            </v-icon>
                          </v-btn>
                         </v-col>
                        </v-row>
                      </v-card-actions>
                 </form>
                </v-card-text>
              </v-container>
             </v-card>
          </v-flex>
       </v-layout>
    
    </v-container>

</template>


<script>
export default {
name: "Login",
data() {
return {
 name: "",
 email: "",
 password: "",
};
},
methods: {
login() {
 const { username } = this;
 console.log(username + "logged in")
},
},
};
</script>