<template>
  <div>
    <nav>
      <div id="logo">
        <nuxt-link to="/"><img src="~assets/images/logo.svg" /></nuxt-link>
      </div>
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
    </nav>
  </div>
</template>

<style scoped lang="scss">
nav {
  height: 135px;
  display: flex;
  justify-content: space-between;
  padding: 0 70px;
  align-items: center;
  #logo img {
    max-height: 64px;
  }
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
}
</style>
