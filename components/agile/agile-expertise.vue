<template>
   <section class="comp comp-agile-expertise">
      <ul class="container container--grid">
        <li>
          <h3>Organize<br /> Facilitate<br /> Coach</h3>
          <p>coaching and scaling agile</p>
        </li>
        <li>
          <h3>Quality<br />  Test<br /> Deploy</h3>
          <p>i still code and intergate automated solutions, continuos integration and deployment</p>
        </li>
        <li>
          <h3>Measure<br /> Learn<br /> Decide</h3>
          <p>like to learn and make educated decisions</p>
        </li>
      </ul>
    </section>
</template>

<style lang="scss">
.comp-agile-expertise {
  .container--grid {
    justify-content: center;
  }
  li {
    list-style: none;
    grid-column-end: span 4;
    &:first-child {
      grid-column-start: 2;
    }
  }
}
</style>
