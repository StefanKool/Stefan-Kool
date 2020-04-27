<template>
  <li class="resume__portfolio-item">
    <div
      class="resume__portfolio-panel"
      :style="{ backgroundColor: backgroundColor }"
    >
      <app-image
        v-if="insetPrimary"
        :imgFileName="insetPrimary"
        :imgWidth="insetPrimaryWidth"
      />
      <app-image
        v-if="insetSecondary"
        :imgFileName="insetSecondary"
        :imgWidth="insetSecondaryWidth"
      />
    </div>
    <span v-if="title" class="type--bold-sc">
      {{ title }}
    </span>
    <p v-if="description">
      {{ description }}
    </p>
  </li>
</template>

<script>
export default {
  name: 'resume-portfolio-item',
  props: {
    title: {
      type: String
    },
    description: {
      type: String
    },
    insetPrimary: {
      type: String
    },
    insetPrimaryWidth: {
      type: Number,
      default: null
    },
    insetSecondary: {
      type: String
    },
    insetSecondaryWidth: {
      type: Number,
      default: null
    },
    backgroundColor: {
      type: String,
      default: 'transparent'
    }
  }
}
</script>

<style lang="scss">
/* add utilities */
@import '~assets/scss/utilities.scss';

.resume-background-c1 {
  background-color: #f3f3f3;
}
.resume-background-c2 {
  background-color: #2a3425;
}
.resume-background-c3 {
  background-color: #dee2de;
}
.resume-background-c4 {
  background-color: #86a27b;
}
.resume-background-c5 {
  background-color: #ffc001;
}
.resume-background-c6 {
  background-color: #abc796;
}
.resume-background-c7 {
  background-color: #c2d4ad;
}
.resume-background-c8 {
  background-color: #fffeca; /* Voorhoede paper */
}
.resume-background-sps {
  background-color: rgba(67, 153, 181, 0.3);
}
.resume-background-psm {
  background-color: rgba(58, 124, 154, 0.3);
}
.resume-background-pspo {
  background-color: rgba(127, 163, 63, 0.3);
}
.resume-background-psd {
  background-color: rgba(207, 70, 39, 0.3);
}
.resume-background-tr {
  background: transparent;
  border: 1px solid #e7e8e1;
}

.resume__portfolio-item {
  flex-basis: 32%;
}

.resume__portfolio-panel {
  height: 124px;
  border-radius: 4px;
  margin-bottom: 0.5rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

.resume__certification-panel {
  border-radius: 4px;
  text-align: center;
  margin-bottom: 0.5rem;
}

.resume__certification-panel img {
  margin: 16px 8px;
  display: inline-block;
}
</style>
