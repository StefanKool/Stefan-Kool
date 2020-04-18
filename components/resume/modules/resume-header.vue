<template>
  <header class="resume__header">
    <div class="container container--grid">
      <div
        class="resume__aside resume--padding"
      >
        <img :src="`~/assets/img/${header.photo.src}`" :width="header.photo.width" :height="header.photo.height" />
      </div>
      <div
        class="resume__body resume--padding no-padding-left"
      >
        <h1 class="mdl-typography--display-5 no-margin">
          <span class="type--regular-sc type--uppercase">{{ header.firstName }}</span
          ><span class="type--thin-cpr-sc type--uppercase">{{ header.surName }}</span>
        </h1>
        <h4 class="type--thin-cpr-sc type--light no-margin">
          {{ header.titles }}
        </h4>
        <div class="resume__download">
          <a :href="header.pdf">
            <i class="fas fa-file-pdf fa-3x"></i>
          </a>
        </div>
        <div class="resume__contact-details">
          <div class="resume__header-item type--thin-cpr-sc">
            <span
              ><i class="fas fa-phone margin-right-2sp"></i
              >{{ header.phone }}</span
            >
          </div>
          <div class="resume__header-item type--thin-cpr-sc">
            <span
              ><i class="fas fa-envelope margin-right-2sp"></i
              >{{ header.email }}</span
            >
          </div>
          <div class="resume__header-item type--thin-cpr-sc">
            <span
              ><i class="fas fa-map-marker margin-right-2sp"></i
              >{{ header.address }}</span
            >
          </div>
          <div class="resume__header-item type--thin-cpr-sc">
            <span
              ><i class="fas fa-birthday-cake margin-right-2sp"></i
              >{{ header.birthdate }}</span
            >
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'resume-header',
  props: {
    header: {
      type: Object
    }
  }
}
</script>

<style lang="scss">
/* add utilities */
@import "~assets/scss/utilities.scss";

.resume__header {
  background-color: $color-brand-primary;
  color: #fff;
  position: relative;
  padding-bottom: 0;
  overflow: hidden;
}

.resume__header img {
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.26), 0 6px 12px rgba(0, 0, 0, 0.43);
  vertical-align: bottom;
}

@media screen and (max-width: 479px) {
  .resume__header img {
    max-width: 200px;
  }
}


.resume__download {
  position: absolute;
  top: 40px;
  right: 40px;
}

@media screen and (max-width: 839px) {
  .resume__download {
    top: 20px;
    right: 20px;
  }
}

.resume__download a {
  color: #ffffff;
  opacity: 0.54;
}

.resume__download a:hover {
  opacity: 1;
}


.resume__header .resume--padding {
  padding-bottom: 0;
  margin-bottom: 0;
}


.no-padding-left {
  padding-left: 0;
}

.resume__header-item {
  font-size: 7pt;
}

.resume__header-item {
  margin-bottom: 0;
}

.resume__header-item span {
  padding-right: 4.5mm;
}

@media screen and (max-width: 479px) {
  .resume__header .resume--padding {
    padding-bottom: 20px;
  }
}

.resume__header-item {
  float: left;
  font-size: 14px;
  line-height: 1;
  margin-bottom: 10px;
}

.header-item--date {
  position: absolute;
  right: 40px;
  bottom: 20px;
}

@media screen and (max-width: 1164px) {
  .resume__header-item {
    width: 50%;
  }
}

@media screen and (max-width: 839px) {
  .resume__header-item {
    width: 100%;
  }
}

@media screen and (max-width: 479px) {
  .resume__header .no-padding-left {
    padding-left: 20px;
  }
}

.resume__header-item span {
  padding-right: 20px;
}

.resume__contact-details {
  bottom: 0;
  position: absolute;
  padding: 10px 0;
}

@media screen and (max-width: 479px) {
  .resume__contact-details {
    bottom: auto;
    position: relative;
  }
}
</style>
