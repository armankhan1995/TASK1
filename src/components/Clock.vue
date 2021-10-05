<template>
  <div class="container" style="width: 30%">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">Clock</h5>
        <div v-show="!show">
          {{ moment().format("MMMM Do YYYY") }}
        </div>
        <div>
          {{ dateTime.hours }}:{{ dateTime.minutes }}:{{ dateTime.seconds }}
        </div>
        <button click="show = !show">show</button>
      </div>
    </div>
  </div>
</template>


<script>
//var moment = require("vue-moment");
var moment = require("moment");
const date = new Date();

export default {
  name: "Clock",

  data() {
    return {
      show: false,

      moment: moment,

      dateTime: {
        hours: date.getHours(),
        minutes: date.getMinutes(),
        seconds: date.getSeconds(),
      },
      timer: undefined,
    };
  },
  methods: {
    setDateTime() {
      const date = new Date.new();
      this.dateTime = {
        hours: date.getHours(),
        minutes: date.getMinutes(),
        seconds: date.getSeconds(),
      };
    },
  },
  beforeMount() {
    this.timer = setInterval(this.setDateTime, 1000);
  },
  beforeUnmount() {
    clearInterval(this.timer);
  },

  // if (value) {
  //    return moment(String(value)).format('MM/DD/YYYY')
  // }
};
</script>