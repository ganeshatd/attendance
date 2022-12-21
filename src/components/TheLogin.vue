<style scoped>
* {
  margin: 0;
  padding: 0;
}

body {
  font-family: "Poppins", sans-serif;
}

.main {
  width: 100vw;
  height: 100vh;
  display: flex;
  color: aliceblue;
  align-items: center;
  background-image: url("https://github.com/DwinaTech/public-images/blob/main/background/Nature-Background.jpeg?raw=true");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: bottom;
}

.container {
  width: 100%;
  height: 100%;
  padding: 20px;
  display: flex;
  margin: 0 auto;
  border-radius: 5px 100px;
  align-items: center;
  flex-direction: column;
  justify-content: center;
}

#square {
  display: flex;
  min-width: 400px;
  min-height: 375px;
  justify-content: center;
  transform-style: preserve-3d;
  transition: all 0.3s ease-in;
  box-shadow: 3px 3px 5px #012a4a;
}

.front,
.right,
.left {
  width: 100%;
  height: 100%;
  padding: 40px;
  display: flex;
  border-radius: 5px;
  position: absolute;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  background-color: #013a63;
  box-shadow: 3px 3px 5px #012a4a;
}

.front {
  transform: translateZ(50px);
}
.container h1 {
  font-size: 35px;
  margin-bottom: 15px;
}

.container .form-container {
  width: 100%;
  display: flex;
  flex-direction: column;
}

.container .form-container .forgot-pw-container{
  cursor: pointer;
  text-decoration: underline;
}

.container .form-container input,
.container .form-container button,
.container .form-container h5 {
  margin-bottom: 15px;
}

.container .form-container input {
  border: 0;
  padding: 10px 8px;
  min-height: 40px;
  font-size: 20px;
  border-radius: 4px;
  border-bottom:1px solid #6886a3;  
  background: #0d4269;
  color: #fff;
  box-sizing: border-box;
}

.container .form-container button {
  border: 0;
  padding: 10px 0;
  outline: none;
  min-height: 30px;
  font-size: 20px;
  border-radius: 4px;
  background-color: aqua;
}

#frontSide {
  display: none;
}
</style>


<template>
  <div>
    <div class="main">
      <div class="container">
        <div id="square">
          <div class="front">
            <h1>Login</h1>
            <div class="form-container">
              <input
                required
                type="email"
                v-model="email"
                id="email"
                placeholder="Email"
              />
              <input
                required
                type="password"
                name="password"
                v-model="password"
                placeholder="Password"
              />
              <button type="submit" @click="LoginUser()">Submit</button>

              <div class="forgot-pw-container" @click="forgotPw()">
                  Forgot Password                
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  name: "TheLogin",
  data() {
    return {
      email: null,
      password: null
    };
  },
  methods: {
    forgotPw() {
      console.log("pw");
      this.$router.replace({ name: "forgot" });
    },
    LoginUser() {
      console.log("Login user");
      axios({
          url: "http://localhost:4000/",
          method: "post",
          data: { "id": "ATD04", "password": "automatad@04"},
        })
          .then(function (res) {
            console.log(res);      
            // this.$router.replace({ name: "form" });
          })
          .catch(function (err) {
            console.log(err);
          });      
    },
  },
};
</script>
