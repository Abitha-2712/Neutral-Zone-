<template>
    <v-app>
       <v-navigation-drawer v-model="drawer" app>
         <v-list>
           <v-list-item @click=" profile()">
              <v-list-item-action>
               <v-icon>mdi-account
               </v-icon>
              </v-list-item-action>
               <v-list-item-title>Profile
               </v-list-item-title>
            </v-list-item>
            
             <v-list-item @click=" help()">
               <v-list-item-action>
                <v-icon>mdi-help-circle
                </v-icon>
               </v-list-item-action>
                <v-list-item-title>Help
                </v-list-item-title>
             </v-list-item>
             <v-list-item @click=" resent()">
               <v-list-item-action>
                <v-icon>mdi-file
                </v-icon>
               </v-list-item-action>
                <v-list-item-title>Resent
                </v-list-item-title>
             </v-list-item>
             <v-list-item @click=" settings()">
                <v-list-item-action>
                 <v-icon>mdi-cog
                 </v-icon>
                </v-list-item-action>
                 <v-list-item-title>Settings
                 </v-list-item-title>
             </v-list-item>
             <v-list-item @click=" clear()">
               <v-list-item-action>
                <v-icon>mdi-delete
                </v-icon>
               </v-list-item-action>
                <v-list-item-title>Clear
                </v-list-item-title>
             </v-list-item>
                <v-spacer></v-spacer> 
                  <v-divider></v-divider>
                    <v-list-item @click="logout" to="/loginpage">
                     <v-list-item-icon>
                      <v-icon>mdi-logout
                      </v-icon>
                     </v-list-item-icon>
                      <v-list-item-title>
                       Logout
                      </v-list-item-title>
                    </v-list-item>
         </v-list>
       </v-navigation-drawer>
     <v-app-bar app color="black" :clipped-left="clipped" fixed>
         <v-app-bar-nav-icon @click.stop="drawer = !drawer" style="color: white;">
         </v-app-bar-nav-icon>
         <v-toolbar-title style="color: white;" class="text-h4">
           Neutral Zone
         </v-toolbar-title>
         <v-spacer></v-spacer>
           <v-btn icon text color="white" @click="logout" to="/loginpage">
             <v-icon>mdi-logout
             </v-icon>
           </v-btn>
       </v-app-bar>
     </v-app>
 </template>
   
   <script >
   export default {
     name:'user_layout',
     async mounted () {
     this.$vuetify.theme.dark = false
   },
   data() {
     return {
       drawer: false,
     };
   }, 
   methods: {
     profile() {
       this.$router.push('/profilee');
     },
     help() {
       this.$router.push('/help');
     },
     settings() {
       this.$router.push('/settings');
     },
  
   }
 
   }
 </script>