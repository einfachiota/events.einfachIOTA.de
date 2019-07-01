<template>
  <div>
    <div class="header">
      <h1 class="header__title">{{event.title}}</h1>
      <div class="divider"></div>
      <!--<div class="image-wrapper">
        <div class="image" v-bind:style="{ 'background-image': 'url(' + event.feature_image + ')' }"></div>
      </div>-->
    </div>
    <Content :content="event.description" />
  </div>
</template>

<script>
import axios from "axios";

const PROVIDER = process.env.VUE_APP_EVENT_PROVIDER;
import Content from "@/components/Content";

export default {
  name: "event",
  params: ["slug"],
  components: {Content},
  data() {
    return {
      event: {}
    };
  },
  methods: {
    fetchPost() {
      let self = this;
      axios
        .get(`${PROVIDER}/events/${this.$route.params.slug}.json`)
        .then(response => {
          // JSON responses are automatically parsed.
          console.log(response);
          self.event = response.data;
        })
        .catch(e => {
          console.log(e);
        });
    }
  },
  created() {
    this.fetchPost();
  }
};
</script>

<style lang="scss">
.header {
  text-align: center;
  &__title {
    margin: 60px 40px 20px 40px;
  }
  .divider {
    margin: 0 auto;
  }
  .image-wrapper {
    margin: 20px auto;
    height: 550px;
    width: 100%;
    max-width: 1080px;
    overflow: hidden;
    margin-bottom: 20px;
    .image {
      height: inherit;
      width: inherit;
      background-size: cover;
      background-position: center center;
      transition: all 300ms ease-in-out;
    }
  }
}
</style>
