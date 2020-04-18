<template>
  <section class="margin-bottom-5sp">
    <h5 class="type--bold-sc">References</h5>
    <div class="type--bold-sc margin-bottom-2sp">
      On request:
    </div>
    <div class="column-row margin-bottom-2sp">
      <div class="resume__reference-person -margin-bottom-1sp">
        <div class="resume__reference-avatar">
          <i class="fas fa-user"></i>
        </div>
        <div
          class="margin-bottom-1sp resume__reference-line reference-line--name"
        >
          <br />
        </div>
        <div
          class="margin-bottom-1sp resume__reference-line reference-line--title"
        >
          <br />
        </div>
      </div>
      <div class="margin-bottom-1sp resume__reference-line">
        <small
          ><i class="fas fa-phone margin-right-2sp"></i
        ></small>
      </div>
      <div class="resume__reference-line">
        <small
          ><i class="fas fa-envelope margin-right-2sp"></i
        ></small>
      </div>
    </div>
    <div class="column-row">
      <div class="resume__reference-person margin-bottom-1sp">
        <div class="resume__reference-avatar">
          <i class="fas fa-user"></i>
        </div>
        <div
          class="margin-bottom-1sp resume__reference-line reference-line--name"
        >
          <br />
        </div>
        <div class="resume__reference-line reference-line--title">
          <br />
        </div>
      </div>
      <div class="margin-bottom-1sp resume__reference-line">
        <small
          ><i class="fas fa-phone margin-right-2sp"></i
        ></small>
      </div>
      <div class="resume__reference-line">
        <small
          ><i class="fas fa-envelope margin-right-2sp"></i
        ></small>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'resume-references'
}
</script>

<style lang="scss">
/* add utilities */
@import "~assets/scss/utilities.scss";


.resume__reference-line {
  padding: 0 1rem;
  line-height: 1.5rem;
  border-radius: 4px;
  background-color: #f3f3f3;
  color: #2a3425;
}

.reference-line--name {
  height: 1.25rem;
}

.reference-line--title {
  height: 1.25rem;
}

.resume__reference-person {
  position: relative;
  padding-left: 3.5rem;
}

.resume__reference-avatar {
  position: absolute;
  left: 0;
  top: 0;
  width: 3rem;
  height: 3rem;
  border-radius: 4px;
  background-color: #f3f3f3;
  color: #192d40;
  line-height: 3rem;
  text-align: center;
}

</style>


