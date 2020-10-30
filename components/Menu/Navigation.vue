<template>
  <div id="navigation">
    <ul>
      <li>
        <nuxt-link to="/">Zgodba</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/">Vino</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/" class="navigation__active">Vinogradi</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/">Kmetija</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/">Kontakt</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
@import '~assets/styles/variables.scss';
#navigation {
  ul {
    display: flex;
    justify-content: space-between;
  }
  ul,
  li {
    gap: 80px;
    list-style: none;
    color: $menuLinkColor;
    font-size: 23px;
    line-height: 30px;
    font-family: LLRG, sans-serif;
    & a:hover {
      color: $menuActiveLinkColor;
    }
  }
  .navigation__active {
    color: $menuActiveLinkColor;
  }
}
</style>
