<template>
  <div class="hello">

  
   
  
    <!-- inputValue : '2 ways', -->

    <!--signup page-->
    <form action="submit-form.php">
    <label for="name">Name: </label>
    <input required type="text" id="name" name="name" placeholder="name" v-model="form.name">
    <br>
    <label for="n1"> Email </label>
   
    <input required type="text" id="n1" name="email" placeholder="@abcd.gmail" v-model="form.email">
    <p v-if="emailError">{{ emailError }}</p>
    <br>
    <label for="n2">Password </label>
    <input required type="text" id="n2" name="password" placeholder="ab11@" v-model="form.password">
    <br>
    <label for="n3">Confirm Password </label>
    <input required type="text" id="n3" name="password" placeholder="ab11@" v-model="form.confirmPassword">
    <br>



    <button >submit </button>
  </form>



  <br>
  <br>
  <br>
  <br>
  <br>
  <br>

<!--1 way binding-->
    <!-- <input type=" "> -->
  </div>
</template>
    
<script>
// import myname from

 
export default {
  name: 'HelloWorld',
  
  components :{
   
  },
  props: {
    msg: String,

   
  },

  data() {
    return {
      // message: "this is mustache",
     
      emailError: '',
      passwordError: '',
      form:{ 
       inputValue : '',
      name: '',
      email : '',
      password: ' ',
      confirmPassword: '',
      // myname: '',
     


      },
      

     

    };
  },
  computed: {

  },
  methods: {
    login() {
      this.validateUsername();
      this.validateEmail();
      this.validatePassword();
      console.log('Form submitted:', this.form);
    },

    validateUsername(name) {
      let Num = false;

      for (let i = 0; i < name.length; i++) {
        if ((name[i] >= '0' && name[i] <= '9') || /[!@#$]/.test(name[i])) {
          Num = true;
        }

        if (name[i] === ' ') {
          return false;
        }
      }

      if (!Num) {
        return false;
      }

      return true;
    },

    validateEmail() {
  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  if (!emailRegex.test(this.form.email)) {
    this.emailError = 'Invalid email address';
    window.alert('Invalid email address');
  } else {
    this.emailError = '';
  }
},


    validatePassword() {
     
      if (this.form.password.length < 8) {
        this.passwordError = ' at least 8 characters';
      } else if (this.form.password.search(/[a-z]/) < 0) {
        this.passwordError = ' must contain one lowercase letter';
      } else if (this.form.password.search(/[A-Z]/) < 0) {
        this.passwordError = ' must contain  one uppercase letter';
      } else if (this.form.password.search(/[0-9]/) < 0) {
        this.passwordError = ' must contain  one number';
      } else {
        this.passwordError = '';
      }
    },
  },





  
  created() {

  },
  mounted() {


  },
  updated() {

    console.log(this.inputValue)
    console.log(this.form.name)
    console.log(this.form.email)
    console.log(this.form.password)


  },  

  unmounted (){

  },
  // destroyed() {

  // }
} ;

</script>


<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
