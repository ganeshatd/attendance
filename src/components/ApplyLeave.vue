
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
  justify-content: center;
}

.cont{
  display: flex;
  justify-content: center;
  align-items: center;
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

.container .form-container .forgot-pw-container{
  cursor: pointer;
  text-decoration: underline;
}


#square {
  display: flex;
  min-width: 400px;
  height: 600px;
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

.actions button {
  border: 0;
  outline: none;
  font-size: 20px;
  min-height: 30px;
  padding: 10px 20px;
  border-radius: 4px;
  background-color: aqua;
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
  color: #fff;  
  border-bottom:1px solid #6886a3;  
  background: #0d4269;
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

.container .actions {
  display: flex;
}

.container .actions button {
  margin-right: 10px;
}
</style>

<template>
  <div>
    <div class="main">
      <div class="cont">
        <div class="container">
          <div id="square">
            <div class="front">
              <h1>Apply Leave</h1>
              <div class="form-container">
                <div>
                  Date
                  <Datepicker
                    v-model="date"
                    range
                    :enable-time-picker="false"
                    style="border: 1px solid gray; margin-bottom: 20px"
                    dark
                  ></Datepicker>
                </div>
                <input
                  required
                  type="text"
                  v-model="ename"
                  id="empname"
                  placeholder="Employee Name"
                />
                <v-select
                  label="Type"
                  :items="[
                    'Sick',
                    'Casual',
                    'Privilaged'
                  ]"
                ></v-select>
                <input
                  required
                  type="text"
                  v-model="reason"
                  id="reason"
                  placeholder="Reason for Leave"
                />
                <v-select
                  label="Manager"
                  :items="managerList"
                ></v-select>
                <button type="submit">Submit</button>
                <div class="forgot-pw-container" @click="logout()">
                  Logout               
                </div>                
              </div>
            </div>
          </div>
        </div>
        <div class="calender-container">
          <iframe
            src="https://calendar.google.com/calendar/embed?src=b21d055c31ee3953cfca82d1777e2e9540da9e3385d9d3dab1b9694ed6c11b70%40group.calendar.google.com&ctz=Asia%2FKolkata"
            style="border: 0"
            width="800"
            height="590"
            frameborder="0"
            scrolling="no"
          ></iframe>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Datepicker from "@vuepic/vue-datepicker";
import "@vuepic/vue-datepicker/dist/main.css";

export default {
  name: "TheLogin",
  components: {
    Datepicker,
  },
  data() {
    return {
      ename: null,
      reason: null,
      date: null,
      managerlist: ['California', 'Colorado', 'Florida', 'Georgia', 'Texas', 'Wyoming']
    }
  },
  methods: {
    LoginUser() {
      console.log("Login user");
      this.$router.replace({ name: "form" });
    },
    logout(){
      console.log("logout");
      this.$router.replace({ name: "home" });
    }
  },
};
</script>
