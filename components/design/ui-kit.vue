<template>
  <section class="comp comp-ui-kit">
    <div class="container container--grid">
      <article class="ui-kit">
        <h2 class="h3 ui-kit-header">Colors</h2>
        <div class="ui-kit-color ui-kit-color--brand-primary">

        </div>
        <div class="ui-kit-color ui-kit-color--brand-error">

        </div>
        <div class="ui-kit-color ui-kit-color--brand-success">

        </div>
        <div class="ui-kit-color ui-kit-color--brand-warn">

        </div>
        <div class="ui-kit-color ui-kit-color--brand-cta">

        </div>
        <h2 class="h3 ui-kit-header">Grid</h2>
        <h2 class="h3 ui-kit-header">Type</h2>
        <h1>
          Dolor sit amet consectetur adipisicing elit.
        </h1>
        <h2>
          Voluptate aspernatur inventore quo est tempore corporis.
        </h2>
        <h3>Inventore quo est tempore corporis maxime odit doloribus.</h3>
        <h4>
          Dolor sit amet consectetur adipisicing elit. Odio, magnam voluptatum.
        </h4>
        <h5>
          Voluptate aspernatur inventore quo est tempore corporis maxime odit
          doloribus.
        </h5>
        <h6>Inventore quo est tempore corporis maxime odit doloribus.</h6>
        <p class="type--intro">
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Odio, magnam
          voluptatum? Consequuntur, sit incidunt? Iure fugiat minima, voluptate
          aspernatur inventore quo est tempore corporis maxime odit doloribus?
          Ad, voluptate quam?
        </p>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Odio, magnam
          voluptatum? Consequuntur, sit incidunt? Iure fugiat minima, voluptate
          aspernatur inventore quo est tempore corporis maxime odit doloribus?
          Ad, voluptate quam?
        </p>
        <img
          src="/_nuxt/assets/img/stefan-print.png"
          width="230"
          height="287"
        />
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Odio, magnam
          voluptatum? Consequuntur, sit incidunt? Iure fugiat minima, voluptate
          aspernatur inventore quo est tempore corporis maxime odit doloribus?
          Ad, voluptate quam?
        </p>
        <p>
          <img
            src="/_nuxt/assets/img/stefan-print.png"
            width="230"
            height="287"
          />
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Odio, magnam
          voluptatum? Consequuntur, sit incidunt? Iure fugiat minima, voluptate
          aspernatur inventore quo est tempore corporis maxime odit doloribus?
          Ad, voluptate quam? Lorem ipsum dolor sit amet consectetur adipisicing
          elit. Totam perspiciatis quis atque fugiat rerum cumque distinctio
          laudantium illum, eos ullam consectetur libero obcaecati aliquam
          similique? Voluptas, officiis? Quo, ipsum sunt.
        </p>
        <h2 class="h3 ui-kit-header">Lists</h2>
        <ul>
          <li>list item</li>
          <li>list item</li>
          <li>list item</li>
        </ul>
        <ol>
          <li>list item</li>
          <li>list item</li>
          <li>list item</li>
        </ol>
        <h2 class="h3 ui-kit-header">Elements</h2>
        <button class="button">button</button>
        <a class="button">button</a>
        <blockquote>Blockquote</blockquote>
        <h2 class="h3 ui-kit-header">Icons</h2>
      </article>
    </div>
  </section>
</template>

<style lang="scss">
/* add utilities */
@import '~assets/scss/utilities.scss';

.ui-kit {
  justify-content: stretch;
  @include media(desktop-and-larger) {
    grid-column-start: 4;
    grid-column-end: span 10;
  }
}

.ui-kit-header {
  border-left: 4px solid var(--color-brand-primary);
  padding: 0.5rem;
  min-height: 7rem;
  background: var(--color-grey-100);
  display: block;
  clear: both;
}

.ui-kit-color {
  width: 5rem;
  height: 5rem;
  margin: 1.5rem 0;
  float: left;
  &.ui-kit-color--brand-primary {
    background: var(--color-brand-primary);
  }
  &.ui-kit-color--brand-error {
    background: var(--color-brand-error);
  }
  &.ui-kit-color--brand-success {
    background: var(--color-brand-success);
  }
  &.ui-kit-color--brand-warn {
    background: var(--color-brand-warn);
  }
  &.ui-kit-color--brand-cta {
    background: var(--color-brand-cta);
  }
}
</style>
