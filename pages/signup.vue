<template>
  <div class="signup-area">
    <div class="signup-inner-area">
       <div class="header-area">
           <div class="logo-area">
                <h5>Signup</h5>
           </div>
       </div>
       <div class="content-area">
            <div class="signup-form">
                <v-form>
    <v-container>
      <v-row>
  
   

        <v-col
          cols="12"
          sm="12"
          md="12"
        >
          <v-text-field
            label="Filled"
            placeholder="Placeholder"
            filled
          ></v-text-field>
        </v-col>

        <v-col
          cols="12"
          sm="12"
          md="12"
        >
          <v-text-field
            label="Outlined"
            outlined
          ></v-text-field>
        </v-col>

     
      </v-row>
    </v-container>
  </v-form>
            </div>
       </div>
    </div>  
  </div>
</template>

<script>
export default {
layout: 'nonehead',
 data () {
    return {
        show1: false,
        show2: true,
        show3: false,
        show4: false,
        password: 'Password',
        rules: {
          required: value => !!value || 'Required.',
          min: v => v.length >= 8 || 'Min 8 characters',
          emailMatch: () => (`The email and password you entered don't match`),
        },
    }
 }
}
</script>

<style lang="scss">
  @import "~/assets/scss/signup.scss";
</style>