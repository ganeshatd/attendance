
<style scoped>
.container{
    border:1px solid #6886a3;  
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
        <h2>{{name}}</h2>
        <h3>{{date}}</h3>
        <h3>{{reason}}</h3>
        <div class="button-container">
            <button type="submit" style="background-color: green;" @click="changeStatus('a')">Approve</button>
            <button type="submit" style="background-color: red;" @click="changeStatus('b')">Reject</button>
        </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "LeaveApproval",
  props: ['name', 'date', 'reason'],
  data() {
    return {
    };
  },
  methods: {
    changeStatus(e){
        console.log('changeStatus', e)
    }
  },
};
</script>
