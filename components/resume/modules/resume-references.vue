<template>
  <section class="mod-references">
    <h5 class="type--bold-sc">References</h5>
    <div class="type--bold-sc">
      On request:
    </div>
    <ul>
      <li class="reference">
        <div class="resume__reference-person">
          <div class="resume__reference-avatar">
            <app-icon :iconId="'user'" />
          </div>
          <div class="resume__reference-line-container" >
            <div class="resume__reference-line reference-line--name">
              <br />
            </div>
            <div class="resume__reference-line reference-line--title">
              <br />
            </div>
          </div>
        </div>
        <div class="resume__reference-line">
          <small><app-icon :iconId="'phone'"/></small>
        </div>
        <div class="resume__reference-line">
          <small><app-icon :iconId="'mail'"/></small>
        </div>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: 'resume-references'
}
</script>

<style lang="scss">
/* add utilities */
@import '~assets/scss/utilities.scss';

.mod-references {
  ul {
    list-style: none;
    padding: 0;
  }
}

.resume__reference-line-container {
  flex-grow: 1;
}

.resume__reference-line {
  padding: 0 1rem;
  line-height: 1.5rem;
  border-radius: 4px;
  background-color: #f3f3f3;
  color: #2a3425;
  margin-bottom: 0.5rem;
}

.reference-line--name {
  height: 1.25rem;
}

.reference-line--title {
  height: 1.25rem;
}

.resume__reference-person {
  position: relative;
  display: flex;
  margin-bottom: 0.5rem;
}

.resume__reference-avatar {
  width: 3rem;
  height: 3rem;
  border-radius: 4px;
  background-color: #f3f3f3;
  color: #192d40;
  line-height: 3rem;
  text-align: center;
  margin-right: 0.5rem;
}
</style>
