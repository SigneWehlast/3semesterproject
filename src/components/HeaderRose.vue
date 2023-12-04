<script>
export default{
    name: "HeaderRose",
    data() {
        return {
            scrolledNav: false,
            mobile: false,
            mobileNav: false,
            windowWidth: null,
        };
    },

    created() {
        window.addEventListener("resize", this.checkScreen);
    },
    mounted() {
        window.addEventListener("scroll", this.updateScroll);
        this.checkScreen();
    },
    methods: {
        toggleMobileNav() {
            this.mobileNav = !this.mobileNav;
        },

        updateScroll() {
            const scrollPosition = window.scrollY;
            this.scrolledNav = scrollPosition > 50;
        },

        checkScreen() {
            this.windowWidth = window.innerWidth;
            this.mobile = this.windowWidth <= 968;
            this.mobileNav = false;
        },
    },
};
</script>

<template>
  <header :class="{'scrolled-nav': scrolledNav}">
      <nav>
        <div class="branding">
          <router-link to="/">
            <img src="../assets/img/logo/logo.png" alt="Logo af DKV">
          </router-link>
        </div>
        <ul v-show="!mobile" class="navigation">
          <li>
            <router-link class="link" :to="{ name: 'program' }" :class="{ 'active': $route.name === 'program' }">
              PROGRAM
            </router-link>
          </li>
          <li>
            <router-link class="link" :to="{ name:'' }" :class="{ 'active': $route.name === '' }">OM PROGRAM
                <i class="fa-solid fa-chevron-down dropdown-ikon"></i>
            </router-link>
            <div class="dropdown-menu">
              <ul>
                <li><router-link :to="{ name: '' }">OM FESTIVALEN</router-link></li>
                <li><router-link :to="{ name: '' }">BILLETINFORMATION</router-link></li>
                <li><router-link :to="{ name: '' }">MERCHANDISE</router-link></li>
                <li><router-link :to="{ name: '' }">PRESSE</router-link></li>
                <li><router-link :to="{ name: '' }">FAQ</router-link></li>
                <li><router-link :to="{ name: '' }">KONTAKT OS</router-link></li>
              </ul>
            </div>
          </li>
          <li>
            <router-link class="link" :to="{ name: '' }" :class="{ 'active': $route.name === '' }">
              VINUDSTILLERE
            </router-link>
          </li>
          <li>
            <router-link class="link" :to="{ name: '' }" :class="{ 'active': $route.name === '' }">
              MAD & DRIKKE
            </router-link>
          </li>
          <li>
            <router-link class="link" :to="{ name: '' }" :class="{ 'active': $route.name === '' }">
              BLIV FRIVILLIG 
            </router-link>
          </li>
          <li>
            <router-link class="link" :to="{ name: '' }" :class="{ 'active': $route.name === '' }">
              GALLERI
            </router-link>
          </li>
          <div class="login-btn">
            <router-link class="login-link" :to="{ name: '' }">Login</router-link>
          </div>
        </ul>
            <div class="icon">
                <i @click="toggleMobileNav" v-show="mobile" class="fa-solid fa-bars" :class="{'icon-active' : mobileNav}"> </i>
            </div>
            <transition name="mobile-nav">
                <ul v-show="mobileNav" class="dropdown-nav">
                    <li><router-link class="link" :to="{ name:'' }">Arbejdsgivere</router-link></li>
                    <li><router-link class="link" :to="{ name:'program' }" :class="{ 'active': $route.name === 'program' }">PROGRAM</router-link></li>
                    <li><router-link class="link" :to="{ name:'' }" :class="{ 'active': $route.name === '' }">OM FESTIVALEN</router-link></li>
                    <li><router-link class="link" :to="{ name:'' }" :class="{ 'active': $route.name === '' }">VINUDSTILLERE</router-link></li>
                    <li><router-link class="link" :to="{ name:'' }" :class="{ 'active': $route.name === '' }">MAD & DRIKKE</router-link></li>
                    <div class="login-btn">
                        <router-link class="login-link" :to="{ name: '' }">Login</router-link>
                    </div>
                </ul>
            </transition>
        </nav>
    </header>
 <!--- <header>
    <div>
      <nav>
        <RouterLink to="/">Forside</RouterLink>
        <RouterLink to="/program">Program</RouterLink>
        <RouterLink to="/om">Om Festivalen</RouterLink>
        <RouterLink to="/billet">Billetinformation</RouterLink>
      </nav>
    </div>
  </header> -->

  <RouterView />
</template>
<style scoped>
header {
	 background-color: transparent;
	 z-index: 999;
	 width: 100%;
	 top: 0;
	 position: fixed;
	 transition: 0.5s ease all;
   background-color: pink;
}
 header nav {
	 position: relative;
	 display: flex;
	 flex-direction: row;
	 padding: 12px 0;
	 transition: 0.5s ease all;
	 width: 90%;
	 margin: 0 auto;
}
 header nav .branding {
	 display: flex;
	 align-items: center;
	 z-index: 999;
}
 header nav .branding img {
	 width: 180px;
	 transition: 0.5s ease all;
}
 header nav .navigation {
	 display: flex;
	 align-items: center;
	 flex: 1;
	 justify-content: flex-end;
}
 header nav .navigation .link {
	 font-size: 14px;
	 transition: 0.5s ease all;
	 padding-bottom: 4px;
	 border-bottom: 1px solid transparent;
	 text-decoration: none;
	 font-weight: 500;
	 color: white;
	 list-style: none;
}
 header nav .navigation .link:hover {
	 border-color: #f3ae3d;
}
 header nav .navigation .link.active {
	 border-bottom: 1px solid #f3ae3d;
}
 header nav .navigation li {
	 padding: 5px;
	 margin-left: 10px;
	 position: relative;
	 list-style: none;
}
 header nav .navigation li .dropdown-menu {
	 display: none;
	 position: absolute;
	 top: 100%;
	 left: 0;
	 width: 100%;
	 padding: 5px;
	 z-index: 10;
}
 header nav .navigation li .dropdown-menu ul {
	 list-style: none;
	 padding: 0;
	 margin: 0;
}
 header nav .navigation li .dropdown-menu ul li {
	 margin-bottom: 10px;
}
 header nav .navigation li .dropdown-menu ul li a {
	 text-decoration: none;
	 font-weight: bold;
}
 header nav .navigation li:hover .dropdown-menu {
	 display: block;
}
 header nav .navigation a {
	 list-style: none;
}
 header nav .login-link {
	 display: inline-block;
	 padding: 8px 16px;
	 font-size: 14px;
	 font-weight: 500;
	 border-radius: 5px;
	 text-transform: uppercase;
	 text-decoration: none;
	 transition: 0.5s ease all;
}
 header nav .login-link .login-btn {
	 display: flex;
	 align-items: center;
}
 header .icon {
	 display: flex;
	 align-items: center;
	 position: absolute;
	 top: 0;
	 right: 24px;
	 height: 100%;
	 z-index: 999;
}
 header i {
	 cursor: pointer;
	 font-size: 24px;
	 transition: 0.8s ease all;
}
 header .icon-active {
	 transform: rotate(180deg);
}
 header .dropdown-nav {
	 display: flex;
	 flex-direction: column;
	 position: fixed;
	 align-items: center;
	 width: 100%;
	 height: 560px;
	 padding-top: 60px;
	 top: 0;
	 left: 0;
   background-color: #f3ae3d;
}
 header .dropdown-nav .link {
	 font-size: 16px;
	 transition: 0.5s ease all;
	 padding-bottom: 4px;
	 border-bottom: 1px solid transparent;
	 text-decoration: none;
	 font-weight: 500;
	 list-style: none;
}
 header .dropdown-nav .link:hover {
	 border-color: #f3ae3d;
}
 header .dropdown-nav li {
	 padding: 16px;
	 margin-left: 16px;
}
 header .dropdown-nav li a {
	 list-style: none;
}
 header .dropdown-nav .login-link {
	 display: inline-block;
	 padding: 8px 16px;
	 font-size: 14px;
	 font-weight: 500;
	 border-radius: 5px;
	 text-transform: uppercase;
	 text-decoration: none;
	 transition: 0.5s ease all;
}
 header .dropdown-nav .login-link .login-btn {
	 display: flex;
	 align-items: center;
}
 @media (min-width: 1176px) {
	 nav {
		 max-width: 11760px;
	}
}
 li::marker {
	 content: none;
}
 
</style>