<template>
  <div class="home">

    <div class="hero">
      <h1 class="heading">Willkommen bei einfachIOTA Events</h1>
      <p class="sub-heading">Die Seite, mit allen Events Rund um IOTA!</p>
    </div>

     <div class="section section-background knowledge">
      <div class="container">
        <h2>Nächstes Event</h2>
        <NextEvent />
      </div>
    </div>

    <div class="section events">
      <div class="container">
        <div class="headline-wrapper">
          <h2>Nächste Events</h2>
          <a href="https://www.einfachiota.de/#/news" target="_blank" tag="button" class="el-button el-button--primary">Alle Neuigkeiten</a>
        </div>
        <div class="divider"></div>
        <LatestNews/>
      </div>
    </div>

    <div class="section section-background knowledge">
      <div class="container">
        <h2>Du bist neu bei IOTA?</h2>
        <p>Dann haben wir genau das Richtige für dich! Die Grundlagen von IOTA haben wir in unserem Wiki für dich zusammengefasst und einfach erklärt, schau mal rein! Wir haben auch Tutorials die man einfach nachmachen kann!</p>
        <a href="https://www.einfachiota.de/" target="_blank" tag="button" class="el-button el-button--primary">Entdecke einfachIOTA</a>

      </div>
    </div>

    <div class="section news">
      <div class="container">
        <div class="headline-wrapper">
          <h2>Neuigkeiten</h2>
          <a href="https://www.einfachiota.de/#/news" target="_blank" tag="button" class="el-button el-button--primary">Alle Neuigkeiten</a>
        </div>
        <div class="divider"></div>
        <LatestNews/>
      </div>
    </div>

    <div class="section section-background knowledge">
      <div class="container">
        <h2>Folge uns oder mach mit</h2>
        <p>Folge uns auf Twitter um immer auf dem neusten Stand zu bleinen. Tritt unsere Discord Server und mach bei der Community mit oder schau auf unserem Gibthub vorbei um dir den Code unserer Projekte anzuschauen!</p>
        <a
          href="https://twitter.com/einfachIOTA"
          target="_blank"
          tag="button"
          class="btn-social el-button el-button--primary"
          style="margin: 0"
        >Twitter</a>
        <a
          href="https://discord.gg/rV3TMSU"
          target="_blank"
          tag="button"
          class="btn-social el-button el-button--primary"
          style="margin: 0 30px 0 30px"
        >Discord</a>
        <a
          href="https://github.com/einfachiota"
          target="_blank"
          tag="button"
          class="btn-social el-button el-button--primary"
          style="margin: 0"
        >Github</a>
      </div>
    </div>

  </div>
</template>

<script>
// @ is an alias to /src
import NextEvent from "@/components/NextEvent.vue";
import NextEvents from "@/components/NextEvents.vue";
import LatestNews from "@/components/LatestNews.vue";

export default {
  name: "home",
  components: {
    NextEvent, NextEvents, LatestNews
  }
};
</script>

<style lang="scss">
.el-main {
  padding: 0px !important;
}
.home {
  text-align: center;
}
.hero {
  margin: 0 10px;
}
.section {
  padding: 80px 0;
  &-background {
    background-color: var(--light);
    p {
      max-width: 600px;
      margin: 15px auto 30px;
    }
    a {
      text-decoration: none;
    }
  }

  .headline-wrapper {
    padding: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
}
@media only screen and (max-width: 740px) {
  .hero {
      padding-top: 40px;
  }
  .headline-wrapper {
    flex-wrap: wrap;
    h2 {
      margin-bottom: 20px;
    }
  }
  .btn-social  {
      margin-bottom: 5px !important;
  }
}

</style>