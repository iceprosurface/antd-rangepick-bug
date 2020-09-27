<template>
  <div id="app">
    <a-range-picker
      :show-time="{
        hideDisabledOptions: true,
        defaultValue: [
          moment('00:00:00', 'HH:mm:ss'),
          moment('23:59:59', 'HH:mm:ss'),
        ],
      }"
      v-model="discountTime"
      format="YYYY-MM-DD HH:mm:ss"
    />
  </div>
</template>

<script>
import moment from "moment";

export default {
  methods: {
    moment,
  },
  name: "App",
  data() {
    const discountTime = [null, null];
    const data = {
      discounted_end_at: "2020-09-26 11:59:59",
      discounted_start_at: "2020-09-25 12:00:00",
    };
    discountTime[0] = moment(data.discounted_start_at);
    discountTime[1] = moment(data.discounted_end_at);
    return {
      discountTime,
    };
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
