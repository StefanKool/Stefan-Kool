<template>
  <section class="margin-bottom-5sp">
    <h5 class="type--bold-sc padding-top-2p">Online</h5>
    <div class="column-row">
      <span class="resume__icon-panel background-color--linkedin"
        ><app-icon :iconId="'linkedin'"
      /></span>
      <nobr
        ><a href="http://bit.ly/2HTALK4" title="my linkedin page"
          >linkedin.com</a
        ></nobr
      >
    </div>
    <div class="column-row">
      <span class="resume__icon-panel background-color--scrum"
        ><app-icon :iconId="'globe'"
      /></span>
      <a href="http://bit.ly/2G3Cdcp" title="my scrum.org page">scrum.org</a>
    </div>
    <div class="column-row">
      <span class="resume__icon-panel background-color--strava"
        ><app-icon :iconId="'strava'"
      /></span>
      <a href="http://bit.ly/2GPScMc" title="my strava page">strava.com</a>
    </div>
    <div class="column-row">
      <span class="resume__icon-panel"><app-icon :iconId="'camera'"/></span>
      <a href="http://bit.ly/2uf95xw" title="my website">stefankool.nl</a>
    </div>
    <div class="column-row">
      <span class="resume__icon-panel color--bitbucket"
        ><app-icon :iconId="'bitbucket'"
      /></span>
      <a href="https://bit.ly/2NoYZig" title="my git repositories"
        >bitbucket.org</a
      >
    </div>
  </section>
</template>

<script>
export default {
  name: 'resume-online'
}
</script>

<style lang="scss">
/* add utilities */
@import '~assets/scss/utilities.scss';

.resume__icon-panel {
  display: inline-block;
  width: 2rem;
  height: 2rem;
  border-radius: 4px;
  color: #2a3425;
  line-height: 2rem;
  text-align: center;
  margin-right: 0.5rem;
  background-color: #f3f3f3;
  background-size: cover;
  background-position: center;
}

// social colors

.color--twitter {
  color: #45a9f7;
}
.color--facebook {
  color: #3c5ba2;
}
.color--youtube {
  color: #bb0000;
}
.color--email {
  color: #e03d19;
}
.color--google {
  color: #dd4b39;
}
.color--whatsapp {
  color: #65bc54;
}
.color--linkedin {
  color: #0177b5;
}
.color--strava {
  color: #fc4c02;
}
.color--bitbucket {
  background-color: #0747a6;
  color: #ffffff;
}

.background-color--linkedin {
  background-color: #0177b5;
  color: #fff;
}
.background-color--strava {
  background-color: #fc4c02;
  color: #fff;
}
.background-color--scrum {
  background-color: #4eabc0;
  color: #fff;
}
</style>
