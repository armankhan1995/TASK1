<template>
  <div class="container" style="width: 30%">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">Clock</h5>
        <div>
          {{ dateTime.hours }}:{{ dateTime.minutes }}:{{ dateTime.seconds }}
        </div>
      </div>
    </div>
  </div>
</template>


<script>
const date = new Date();

export default {
  name: "Clock",

  data() {
    return {
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
};
</script>