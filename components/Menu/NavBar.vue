<template>
  <div>
    <header class="header">
      <nuxt-link to="/">
        <img src="~assets/images/logo.svg" class="logo" />
      </nuxt-link>
      <input id="menu-btn" class="menu-btn" type="checkbox" />
      <label class="menu-icon" for="menu-btn">
        <span class="navicon"></span>
      </label>
      <ul class="menu">
        <li>
          <nuxt-link to="/">Zgodba</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/">Vino</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/" class="active">Vinogradi</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/">Kmetija</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/">Kontakt</nuxt-link>
        </li>
      </ul>
      <div class="language-switcher">
        <ul>
          <li>
            <nuxt-link to="/" class="active">Slo</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/">Ang</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/">De</nuxt-link>
          </li>
        </ul>
      </div>
    </header>
  </div>
</template>

<style scoped lang="scss">
@import '~assets/styles/variables.scss';
.header {
  background-color: #fff;
  width: 100%;
  z-index: 100;
  padding: 20px 20px;
  transition: 1s;
  .active {
    color: $menuActiveLinkColor;
  }
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
    overflow: hidden;
    background-color: #fff;
    align-items: center;
    li {
      padding: 10px;
    }
  }
}
.header .menu-btn {
  display: none;
}
.header li a:hover {
  color: $menuActiveLinkColor;
}
.header .logo {
  max-height: 50px;
}
.header .menu {
  clear: both;
  max-height: 0;
  transition: max-height 0.4s ease-out;
  font-size: 20px;
}
.language-switcher {
  display: none;
  ul {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    li {
      a {
        color: #aeadae;
      }
    }
  }
}
.header .menu-icon {
  cursor: pointer;
  display: inline-block;
  float: right;
  padding: 28px 20px;
  position: relative;
  user-select: none;
}
.header .menu-icon .navicon {
  background: #333;
  display: block;
  height: 2px;
  position: relative;
  transition: background 0.4s ease-out;
  width: 18px;
}
.header .menu-icon .navicon::before,
.header .menu-icon .navicon::after {
  background: #333;
  content: '';
  display: block;
  height: 100%;
  position: absolute;
  transition: all 0.2s ease-out;
  width: 100%;
}
.header .menu-icon .navicon::before {
  top: 5px;
}
.header .menu-icon .navicon::after {
  top: -5px;
}
.header .menu-btn:checked ~ .menu,
.header .menu-btn:checked ~ .language-switcher {
  max-height: 240px;
  display: block;
}
.header .menu-btn:checked ~ .menu-icon .navicon {
  background: transparent;
}
.header .menu-btn:checked ~ .menu-icon .navicon::before {
  transform: rotate(-45deg);
}
.header .menu-btn:checked ~ .menu-icon .navicon::after {
  transform: rotate(45deg);
}
.header .menu-btn:checked ~ .menu-icon:not(.steps) .navicon::before,
.header .menu-btn:checked ~ .menu-icon:not(.steps) .navicon::after {
  top: 0;
}
@media (min-width: $mWidthMedium) {
  .language-switcher {
    display: block;
    ul {
      flex-direction: column !important;
      gap: 5px !important;
      margin-top: 4px;
    }
    ul,
    li {
      color: $menuLinkColor !important;
      font-family: CourierPrime, sans-serif !important;
      font-size: 18px !important;
      line-height: 20px !important;
      & a:hover {
        color: $menuActiveLinkColor !important;
      }
    }
  }
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 135px;
    padding: 0 70px;
    transition: 1s;
    max-width: $maxContainerWidth;
    ul {
      z-index: 99;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      overflow: visible;
      li {
        padding: 0;
      }
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
    .logo {
      max-height: 64px;
    }
  }
  .header .menu-icon {
    display: none;
  }
}
</style>
