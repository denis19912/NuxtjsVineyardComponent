<template>
  <div id="language-switcher">
    <ul>
      <li>
        <nuxt-link to="/" class="language-switcher__active">Slo</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/">Ang</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/">De</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
@import '~assets/styles/variables.scss';
#language-switcher {
  ul {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  ul,
  li {
    list-style: none;
    color: $menuLinkColor;
    font-size: 18px;
    line-height: 20px;
    & a:hover {
      color: $menuActiveLinkColor;
    }
  }
  .language-switcher__active {
    color: $menuActiveLinkColor;
  }
}
</style>
