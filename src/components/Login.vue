<template>
  <div class="flex-container">
    <div class="nav-container">
      <div class="wrapper" id="wrapper">
        <nav id="exmp" class="nav-horiz">
          <img src="../assets/web_logo.png" class="logo" />
          <button v-on:click="reset" class="login-button" id="login">
            Login
          </button>
          <p class="separator" id="separator">|</p>
          <div id="exmp">
            <button
              v-on:click="transition"
              id="signup-button"
              class="signup-button"
            >
              Sign up
            </button>
          </div>
        </nav>
      </div>
    </div>
    {{ info.USD }}
    <form class="example-form" id="example-form">
      <div class="email-input">
        <md-field>
          <label>Email</label>
          <md-input v-model="email"></md-input>
        </md-field>
      </div>
      <div class="password-input">
        <md-field>
          <label>Password</label>
          <md-input type="password" v-model="password"></md-input>
        </md-field>
      </div>
      <a class="forgot-password" href="">Forgot Password?</a>
      <md-button class="md-primary-raised">Login</md-button>
    </form>
    <div class="right-wrapper" id="right-wrapper"></div>
    <div id="righ-nav" class="right-nav-container">
      <h2 id="text-1" class="text-1">Welcome,</h2>
      <h5 id="text-2" class="text-2">
        Please login to assess your performance, find best practices and set the
        benchmark in the sports venue industry.
      </h5>
      <img
        src="../assets/undraw_authentication_fsn5.svg"
        id="auth-icon"
        class="auth-icon"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data: () => ({
    info: null,
    email: null,
    password: null,
  }),
  mounted() {
    axios
      .get("https://api.coindesk.com/v1/bpi/currentprice.json")
      .then((response) => (this.info = response.data.bpi));
  },
  methods: {
    transition: () => {
      document.getElementById("right-wrapper").id = "move";
      document.getElementById("example-form").id = "example-form-after";
      document.getElementById("login").id = "login-after";
      document.getElementById("separator").id = "separator-after";
      document.getElementById("signup-button").id = "signup-after";
      document.getElementById("auth-icon").id = "auth-icon-after";
      document.getElementById("text-1").id = "text-1-after";
      document.getElementById("text-1-after").innerHTML =
        "Measure and Manage your Impact";
      document.getElementById("text-2").isContentEditable = "text-2-after";
      document.getElementById("text-2-after").innerHTML =
        "• Assess your sports venue’s performance. \n • Adjust and set goals to improve your impact. \n • Benchmarking against industry peers. \n • Learn how to make your stadium even more sustainable.";
    },
    reset: () => {
      document.getElementById("move").id = "right-wrapper";
      document.getElementById("login-after").id = "login";
      document.getElementById("signup-after").id = "signup-button";
      document.getElementById("separator-after").id = "separator";
      document.getElementById("auth-icon-after").id = "auth-icon";
      document.getElementById("example-form-after").id = "example-form";
      document.getElementById("text-1-after").id = "text-1";
      document.getElementById("text-1").innerHTML = "Welcome,";
      document.getElementById("text-2-after").id = "text-2";
      document.getElementById("text-2").innerHTML =
        "Please login to assess your performance, find best practices and set the benchmark in the sports venue industry.";
    },
  },
};
</script>

<style>
#move {
  background: linear-gradient(206.13deg, #3333ff 0.85%, #6fcf97 73.7%);
  position: fixed;
  z-index: -1;
  top: -5px;
  height: 100%;
  background-position: left;
  left: 0px;
  width: 50%;
  -webkit-transition: 1s;
}
.logo {
  position: absolute;
  width: 130px;
  height: 50px;
  left: 24px;
  top: -50px;
}
#right-wrapper {
  background: linear-gradient(206.13deg, #3333ff 0.85%, #6fcf97 73.7%);
  position: fixed;
  z-index: -1;
  left: 720px;
  top: -50px;
  width: 100%;
  height: 100%;
  background-position: right;
  -webkit-transition: 1s;
}

#login {
  background-color: Transparent;
  background-repeat: no-repeat;
  border: none;
  cursor: pointer;
  overflow: hidden;
  outline: none;
  color: #404040;
  font-family: "Roboto", sans-serif;
  font-weight: 500;
  font-size: 18px;
  line-height: 20px;
  position: absolute;
  left: 590px;
  top: -40px;
  -webkit-transition: 1s;
}

#login-after {
  left: 750px;
  font-weight: 400;
  opacity: 40;
  -webkit-transition: 1s;
  background-color: Transparent;
  background-repeat: no-repeat;
  border: none;
  cursor: pointer;
  overflow: hidden;
  outline: none;
  color: #404040;
  font-family: "Roboto", sans-serif;
  font-size: 18px;
  line-height: 20px;
  position: absolute;
  top: -40px;
}
#signup-button {
  background-color: Transparent;
  background-repeat: no-repeat;
  color: #404040;
  opacity: 40%;
  border: none;
  cursor: pointer;
  overflow: hidden;
  outline: none;
  font-family: "Roboto", sans-serif;
  font-weight: 400;
  font-size: 18px;
  line-height: 20px;
  position: absolute;
  left: 645px;
  top: -40px;
  -webkit-transition: 1s;
}

#signup-after {
  background-color: Transparent;
  background-repeat: no-repeat;
  color: #404040;
  border: none;
  cursor: pointer;
  overflow: hidden;
  outline: none;
  font-family: "Roboto", sans-serif;
  font-size: 18px;
  line-height: 20px;
  position: absolute;
  top: -40px;
  left: 808px;
  font-weight: 500;
  opacity: 100;
  -webkit-transition: 1s;
}

#separator {
  font-family: "Roboto", sans-serif;
  font-weight: 400;
  font-size: 25px;
  line-height: 20px;
  position: absolute;
  left: 644px;
  top: -65px;
  color: #404040;
  opacity: 40%;
  -webkit-transition: 1s;
}

#separator-after {
  font-family: "Roboto", sans-serif;
  font-weight: 400;
  opacity: 40%;
  font-size: 25px;
  line-height: 20px;
  position: absolute;
  top: -65px;
  color: #999999;
  left: 805px;
  -webkit-transition: 1s;
}

.flex-container .right-nav-container {
  z-index: 50;
}
#text-1 {
  position: absolute;
  width: 50%;
  text-align: left;
  height: 20px;
  left: 792px;
  top: 27px;
  z-index: 50;
  padding-left: 30px;
  font-family: "Roboto", sans-serif;
  font-weight: bold;
  font-size: 48px;
  line-height: 20px;
  color: #fff;
  -webkit-transition: 1s;
}

#text-1-after {
  position: absolute;
  width: 50%;
  text-align: left;
  height: 20px;
  top: 27px;
  z-index: 50;
  padding-left: 30px;
  font-family: "Roboto", sans-serif;
  font-weight: bold;
  font-size: 48px;
  color: #fff;
  left: 20px;
  line-height: 50px;
  -webkit-transition: 1s;
}

#text-2 {
  position: absolute;
  text-align: left;
  width: 600px;
  height: 45px;
  left: 775px;
  top: 75px;
  z-index: 50;
  padding-left: 50px;
  font-family: Roboto;
  font-style: normal;
  font-weight: 300;
  font-size: 18px;
  line-height: 25px;
  color: #fff;
  -webkit-transition: 1s;
}
#text-2-after {
  position: absolute;
  text-align: left;
  width: 600px;
  height: 45px;
  top: 75px;
  z-index: 50;
  padding-left: 50px;
  font-family: Roboto;
  font-style: normal;
  font-weight: 300;
  font-size: 18px;
  line-height: 25px;
  color: #fff;
  left: 0px;
  padding-top: 70px;
  -webkit-transition: 1s;
}

#auth-icon {
  position: absolute;
  width: 663px;
  height: 458px;
  z-index: 50;
  left: 809px;
  top: 201px;
  visibility: visible;
  opacity: 1;
  transition: visibility 0s 1s, opacity 1s linear;
}

#auth-icon-after {
  position: absolute;
  width: 663px;
  height: 458px;
  z-index: 50;
  left: 809px;
  top: 201px;
  visibility: hidden;
  opacity: 0;
  transition: visibility 0s 1s, opacity 1s linear;
}
#example-form {
  position: absolute;
  width: 339px;
  height: 272px;
  left: 181px;
  top: 0px;
  opacity: 1;
  transition: visibility 0s 0.5s, opacity 0.5s linear;
}

#example-form-after {
  position: absolute;
  width: 339px;
  height: 272px;
  left: 181px;
  top: 0px;
  opacity: 0;
  transition: visibility 0s 0.5s, opacity 0.5s linear;
}

.example-form .md-primary-raised {
  position: relative;
  left: 0px;
  width: 349px;
  height: 50px;
  top: 300px;
  bottom: 0%;
  font-family: "Roboto", sans-serif;
  font-weight: bold;
  color: #0e3b43;
  font-size: 18px;
  background: #6fcf97;
  border-radius: 13px;
}

.example-full-width {
  width: 100%;
}

.example-form .email-input {
  position: relative;
  left: 17px;
  top: 200px;
}

.example-form .password-input {
  position: relative;
  left: 17px;
  top: 250px;
}

.example-form .forgot-password {
  position: absolute;
  width: 100%;
  height: 20px;
  left: 127px;
  top: 400px;

  font-family: Roboto;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  text-decoration-line: underline;

  color: #000000;
}
</style>
