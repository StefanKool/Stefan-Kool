<template>
  <header class="comp comp-agile-header">
    <div class="container container--max-10-col">
      <h1 class="display-5">
        <span class="type--regular-sc type--uppercase">Stefan</span><span class="type--thin-cpr-sc type--uppercase">Kool</span>
      </h1>
      <h2 class="h6 type--thin-cpr-sc">Certified Scrum master based in Rotterdam the Netherlands</h2>
    </div>
    <div class="card card-4">
      <div>
        <img src="~/static/img/badge-psmii.svg" width="70" height="119" />
        <img src="~/static/img/badge-sps.svg" width="70" height="119" /><br />
        <img src="~/static/img/badge-psmi.svg" width="70" height="119" />
        <img src="~/static/img/badge-pspoi.svg" width="70" height="119" />
        <img src="~/static/img/badge-psdi.svg" width="70" height="119" />
      </div>
    </div>
  </header>
</template>


<style lang="scss">
/* add utilities */
@import "~assets/scss/utilities.scss";


.comp-agile-header {
  position: relative;
  background-color: $color-brand-primary;
  color: $color-grey-0;
  padding: 120px 0;

  h1, h2 {
    text-align: center;
  }
}

.card {
  position: absolute;
  right: 0;
  bottom: -40%;
  z-index: 1;
  background: #fff;
  border-radius: 30px 0 0 30px;
  width: auto;
  transform: skewY(-10deg);
  box-shadow: 0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22);
  & div {
    transform: skewY(10deg);
    padding: 30px;
    color: $color-grey-1000;
    text-align: center;
  }
  & img {
    margin-right: 15px;
    &:last-child {
      margin-right: 0;
    }
  }
}

.display-5 {
  font-size: 76px;
  margin: 0;
}

</style>
