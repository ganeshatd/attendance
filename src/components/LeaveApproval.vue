
<style scoped>
.container {
  border: 1px solid #6886a3;
  background-color: #0d4269;
  width: 320px;
  height: 170px;
  padding-left: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.button-container button {
  border: 0;
  padding: 10px 0;
  outline: none;
  min-height: 30px;
  width: 130px;
  font-size: 20px;
  border-radius: 4px;
  background-color: aqua;
  margin-right: 15px;
  margin-top: 5px;
}
</style>

<template>
  <div>
    <div class="container">
      <h2>{{ name }}</h2>
      <h3>{{ date }}</h3>
      <h3>{{ reason }}</h3>
      <div class="button-container">
        <button
          type="submit"
          style="background-color: green"
          @click="changeStatus('a')"
        >
          Approve
        </button>
        <button
          type="submit"
          style="background-color: red"
          @click="changeStatus('b')"
        >
          Reject
        </button>
      </div>
    </div>
  </div>
</template>
<script>
import axios from 'axios'

export default {
  name: "LeaveApproval",
  props: ["name", "date", "reason"],
  data() {
    return {};
  },
  methods: {
    changeStatus(e) {
      console.log("changeStatus", e);
      if (e == "a") {
        console.log("approve")
        axios({
          url: "http://localhost:3000/createEvent",
          method: "post",
          data: {
            summary: "My second event!",
            location: "Hyderabad,India",
            description: "First event with nodeJS!",
            start: {
              dateTime: "2022-12-21T09:00:00-10:00",
              timeZone: "Asia/Dhaka",
            },
            end: {
              dateTime: "2022-12-23T17:00:00-13:00",
              timeZone: "Asia/Dhaka",
            },
            attendees: [],
            reminders: {
              useDefault: false,
              overrides: [
                { method: "email", minutes: 24 * 60 },
                { method: "popup", minutes: 10 },
              ],
            },
          },
        })
          .then(function (res) {
            console.log(res);
          })
          .catch(function (err) {
            console.log(err);
          });
      }
    },
  },
};
</script>
