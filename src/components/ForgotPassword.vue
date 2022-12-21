
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
  min-height: 300px;
  justify-content: center;
  transform-style: preserve-3d;
  transition: all 0.3s ease-in;
  box-shadow: 3px 3px 5px #012a4a;
}

.front {
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
  margin-top: 25px;
  margin-bottom: 25px;
  flex-direction: column;
}

.container .form-container input,
.container .form-container h5 {
  margin-bottom: 15px;
}

.container .form-container input {
  border: 0;
  padding: 10px 8px;
  min-height: 40px;
  font-size: 20px;
  border-radius: 4px;
  box-sizing: border-box;
}

.container .button-container{
  display: flex;
  justify-content: space-evenly;

}
.container .button-container button {
  border: 0;
  padding: 10px 0;
  outline: none;
  min-height: 30px;
  width: 100px;
  font-size: 20px;
  border-radius: 4px;
  background-color: aqua;
}
#frontSide {
  display: none;
}

.container .actions {
  display: flex;
}
</style>

<template>
  <div>
    <div class="main">
      <div class="container">
        <div id="square">
          <div class="front">
            <h3>Forgot Password</h3>
            <div class="form-container">
              <input
                required
                type="email"
                name="email"
                id="email"
                placeholder="Enter your email address.."
              />

              <div class="button-container">
                <button type="submit" @click="ResetPw">Submit</button>
                <button type="submit" @click="goHome">Cancel</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "ForgotPassword",
  data() {
    return {
    };
  },
  methods: {
    ResetPw(){
      console.log("pw")
    },
    goHome(){
      console.log("Login user")
      this.$router.replace({ name: 'home' });
    }

  },
};
</script>
