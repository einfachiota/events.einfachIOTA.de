<template>
  <div class="event">
    <h3>{{event.title}}</h3>
    <br>
    <VueCountdown :time="startTimeInSeconds(event.start_on)">
      <template
        slot-scope="props"
      >Startet in {{ props.days }} Tagen, {{ props.hours }} Stunden, {{ props.minutes }} Minuten und {{ props.seconds }} Sekunden.</template>
    </VueCountdown>
  </div>
</template>

<script>
import axios from "axios";
import VueCountdown from "@chenfengyuan/vue-countdown";

const PROVIDER = process.env.VUE_APP_EVENT_PROVIDER;

export default {
  name: "NextEvent",
  components: { VueCountdown }, 
  data() {
    return {
      event: {
          start_on: 0
      }
    };
  },
  created() {
    let self = this;
    axios
      .get(`${PROVIDER}/next_event.json`)
      .then(response => {
        // JSON responses are automatically parsed.
        console.log(response);
        self.event = response.data;
      })
      .catch(e => {
        console.log(e);
      });
  },
  methods: {
      startTimeInSeconds(val) {
          let seconds = new Date(val);
          console.log("this.event.starts_o", val)
          if(seconds > 0) {

            var now = new Date().getTime();

            // Find the distance between now and the count down date
            seconds = seconds - now;
            console.log("seconds", seconds)
          } else {
                        console.log("ne")

          }
       
        return seconds

      }
  }
};
</script>

<style lang="scss">
</style>
