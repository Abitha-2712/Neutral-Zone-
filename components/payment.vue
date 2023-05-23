<template>
 
    <v-container fluid fill-height>
        
      <v-card
      class="mx-auto"
      width="400"
      color="white">
      <h3 class="text-h6 text-center " style="padding:5%; color:black">Payment Page</h3>
      <v-container style="width: 100%;">
        <v-card-text style="color:black">
          <form ref="form" @submit.prevent="login()"> 
            <v-text-field
              v-model="email"
              color="primary"
              label="Email"
              type="str"
              variant="underlined">
            </v-text-field>
  
            <v-text-field
              v-model="amount"
              color="primary"
              label="Amount"
              type="float"
              variant="underlined">
            </v-text-field> 
           
            <v-select
          :items="items"
          label="Mode"
        ></v-select>
       


    <v-row>
   
      <v-menu
        ref="menu"
        v-model="menu"
        :close-on-content-click="false"
        :return-value.sync="date"
        transition="scale-transition"
        offset-y
        min-width="auto"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-text-field
            v-model="date"
            label="Date"
            prepend-icon="mdi-calendar"
            readonly
            v-bind="attrs"
            v-on="on"
          ></v-text-field>
        </template>
        <v-date-picker
          v-model="date"
          no-title
          scrollable
        >
          <v-spacer></v-spacer>
          <v-btn
            text
            color="primary"
            @click="menu = false"
          >
            Cancel
          </v-btn>
          <v-btn
            text
            color="primary"
            @click="$refs.menu.save(date)"
          >
            OK
          </v-btn>
        </v-date-picker>
      </v-menu>
      </v-row>
      <v-row>
   
      <v-menu
        ref="menu"
        v-model="menu2"
        :close-on-content-click="false"
        :nudge-right="40"
        :return-value.sync="time"
        transition="scale-transition"
        offset-y
        max-width="290px"
        min-width="290px"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-text-field
            v-model="time"
            label="Time"
            prepend-icon="mdi-clock-time-four-outline"
            readonly
            v-bind="attrs"
            v-on="on"
          ></v-text-field>
        </template>
        <v-time-picker
          v-if="menu2"
          v-model="time"
          full-width
          @click:minute="$refs.menu.save(time)"
        ></v-time-picker>
      </v-menu>
    
    </v-row> 

          </form>
        </v-card-text>
      </v-container>
  
       <v-divider></v-divider>
  
        <v-card-actions>
         <v-spacer></v-spacer>
  
           <v-btn text color="black" block to="/profilepage">
            submitted
  
            <v-icon icon="mdi-chevron-right" end></v-icon>
           </v-btn>
       </v-card-actions>
    </v-card>
  </v-container>

</template>
  


<script>
  export default {
    data: () => ({
      items: ['GPay', 'PhonePay', 'Paytm'],
      date: (new Date(Date.now() - (new Date()).getTimezoneOffset() * 60000)).toISOString().substr(0, 10),
      menu: false,
      modal: false,
      menu2: false,
    data () {
      return {
        time: null,
        menu2: false,
        modal2: false,
      }
    },
   }),
  }
</script>