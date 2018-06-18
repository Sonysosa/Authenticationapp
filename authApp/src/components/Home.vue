<template>
  <div class="row">
    <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12">
      <div class="card">
        <div class="row">
          <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12">
            <h1 class="card-head">SignUp Now!! </h1>
          </div>
        </div>
        <div class="row">
          <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12">
            <input type="text" v-model="email" name="email" placeholder="Email" id="email">
          </div>
        </div>
        <div class="row">
          <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12">
           <input type="password" v-model="password" name="password" placeholder="Password" id="password">
          </div>
        </div>
        <div class="row">
          <div class="col-xs-3 col-sm-3 col-md-3 col-lg-3">
            <label class="checkbox">
            <input type="checkbox" v-on:click="checking">
            <span class="checkmark"></span>
            </label>
          </div>
          <div class="col-xs-9 col-sm-9 col-md-9 col-lg-9">
            <p class="show-password">Show password</p>
          </div>
        </div>
        <div class="row ">
          <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12">
            <p class="button"  v-on:click="validation" >Signup</p>
           </div>
        </div>
        <div class="row">
          <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12">
            <p class="footer">Already have an account? <a v-bind:href="url">Login</a>  </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      email: '',
      password: '',
      url: 'http://localhost:8081/Login'
    }
  },
  methods: {
    checking: function () {
      var x = document.getElementById('password')
      // alert('ahahh')
      if (x.type === 'password') {
        x.type = 'text'
      } else {
        x.type = 'password'
      }
    },
    validation: function () {
      var e = this.email
      var p = this.password
      // alert('haii')
      this.emailValidation(e)
      this.passwordValidation(p)
      this.checkValidation(e, p)
      this.storeValue(e, p)
    },
    emailValidation: function (e) {
      // alert('email validation')
      var mailformat = /[A-Z0-9._%+-]+@[A-Z0-9.-]+.[A-Z]{2,4}/igm
      if (e.match(mailformat)) {
        return true
      } else {
        alert('Enter a valid email address!')
        return false
      }
    },
    passwordValidation: function (p) {
      // alert('password validation')
      var passformat = /^(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,16}$/
      if (p.match(passformat)) {
        alert('your password correct')
        return true
      } else {
        alert('Password must be at least 8 -16 digits one alphabet one special character.')
        return false
      }
    },
    checkValidation: function (e, p) {
      // alert('check')
      if (this.emailValidation(e) === true && this.passwordValidation(p) === true) {
        this.$router.push({path: '/Login'})
      }
    },
    storeValue: function (e, p) {
      // alert('haii')
      this.$localStorage.set('s', true)
      this.$localStorage.set('ekey', e)
      this.$localStorage.set('pkey', p)
    }
  }
}
</script>
<style>
body {
  background-color:#f1f2f2;
}

.card {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  margin-left: 430px;
  transition: 0.2s;
  width: 30%;
  margin-top: 130px;
  background-color: #fff;
  height: 350px;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

.card-head {
  text-align: center;
  font-size: 2em;
  color: #264e86;
  padding-top: 15px;
  font-family: 'Libre Baskerville', serif;
}

#email {
  margin-top: 13px;
  margin-left: 65px;
  border: 1px solid #d4d6c8;
  font-size: 1.1em;
  padding-top: 5px;
  padding-bottom: 5px;
  width: 62%;
  font-family: 'Libre Baskerville', serif;
}

#password {
  margin-top: 15px;
  margin-left: 65px;
  border: 1px solid #d4d6c8;
  font-size: 1.1em;
  padding-top: 5px;
  padding-bottom: 5px;
  width: 62%;
  font-family: 'Libre Baskerville', serif;
}

.button {
  width: 62%;
  background-color: #0074e4;
  margin-left: 65px;
  padding-top: 3px;
  margin-top: 10px;
  text-align: center;
  height: 35px;
  color: white;
  font-size: 1.3em;
  cursor: pointer;
  font-family: 'Libre Baskerville', serif;
}

.checkbox input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
}

.checkmark {
  position: absolute;
  top: 0;
  left: 0;
  height: 28px;
  width: 28px;
  background-color: #f1f2f2;
  margin-left: 64px;
  margin-top: 5px;
}

.checkbox:hover input ~ .checkmark {
  background-color: #ccc;
}

.checkbox input:checked ~ .checkmark {
  background-color: #264e86;
}

.checkmark:after {
  content: "";
  position: absolute;
  display: none;
}

.checkbox input:checked ~ .checkmark:after {
  display: block;
}

.checkbox .checkmark:after {
  left: 9px;
  top: 5px;
  width: 5px;
  height: 12px;
  border: solid white;
  border-width: 0 3px 3px 0;
  -webkit-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  transform: rotate(45deg);
}

.show-password {
  margin-top: 10px;
  font-size: 1.3em;
  font-family: 'Libre Baskerville', serif;
  margin-top: 15px;
}

.footer {
  font-size: 1.2em;
  margin-left: 64px;
}
</style>
