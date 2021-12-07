<template>
  <v-app>
 
  	<v-navigation-drawer v-if="drawer" v-model="drawer" :mini-variant="miniVariant" :clipped="clipped"
      fixed
      app>
      <v-list>
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to"
          router
          exact >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
	    	<v-list-item >
          <v-list-item-content>
           <v-btn elevation="2" to='/signup' class="btn-primary btn-join-eden" >Join Eden</v-btn>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" class="header-area"  fixed app >
 
  <div class="menu" :class="classTogglemenu" v-on:click="menuClick()">
    
    <span class="menu-circle"></span>
      <a href="#" class="menu-link">
        <span class="menu-icon">
          <span class="menu-line menu-line-1"></span>
          <span class="menu-line menu-line-2"></span>
          <span class="menu-line menu-line-3"></span>
        </span>
      </a>
  </div>

  <div class="menu-overlay" :class="classTogglemenu" v-on:click="menuClick()">
   <div id="circle-orbit-container">

  <!-- Circles closest to the central point -->
  <div id="inner-orbit">
    <div class="inner-orbit-cirlces"></div>
  </div>
<div class="line-inner-orbit"></div>
  <!-- Circles second closest to the central point -->
  <div id="middle-orbit">
    <div class="middle-orbit-cirlces"></div>
  </div>
<div class="line-middle-orbit"></div>
<div class="line-middle2-orbit"></div>
<div class="line-outer-orbit"></div>
  <!-- Circles furthest away to the central point -->
  <div id="outer-orbit">
    <div class="outer-orbit-cirlces"></div>
  </div>
<div id="outer4-orbit">
    <div class="outer4-orbit-cirlces"></div>
  </div>
</div>
    <a href="#about-section" class="menu-about" >About</a>
    <a href="#features-section" class="menu-features">Features</a>
    <a href="#distribution-section" class="menu-distribution">Distribution</a>
    <a href="#roadmap-section" class="menu-roadmap">Roadmap</a>
    <a href="#faq-section" class="menu-join-eden">Join eden</a>
  </div>
    <!-- <v-dialog
      v-model="dialog"
      fullscreen
      hide-overlay
      transition="dialog-bottom-transition"
    >
      <template v-slot:activator="{ on, attrs }">
         <a  class="hamburger-menu" href="#" title="Menu" v-bind="attrs" v-on="on">
          <span class="line line-1"></span>
          <span class="line line-2"></span>
          <span class="line line-3"></span>
        </a>

      </template>
      <v-card>
        <v-toolbar
          dark
          color="primary"
        >
          <v-btn
            icon
            dark
            @click="dialog = false"
          >
            <v-icon>mdi-close</v-icon>
          </v-btn>
          <v-toolbar-title>Settings</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-toolbar-items>
            <v-btn
              dark
              text
              @click="dialog = false"
            >
              Save
            </v-btn>
          </v-toolbar-items>
        </v-toolbar>
        <v-list
          three-line
          subheader
        >
          <v-subheader>User Controls</v-subheader>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>Content filtering</v-list-item-title>
              <v-list-item-subtitle>Set the content filtering level to restrict apps that can be downloaded</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>Password</v-list-item-title>
              <v-list-item-subtitle>Require password for purchase or use password to restrict purchase</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list
          three-line
          subheader
        >
          <v-subheader>General</v-subheader>
          <v-list-item>
            <v-list-item-action>
              <v-checkbox v-model="notifications"></v-checkbox>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Notifications</v-list-item-title>
              <v-list-item-subtitle>Notify me about updates to apps or games that I downloaded</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-action>
              <v-checkbox v-model="sound"></v-checkbox>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Sound</v-list-item-title>
              <v-list-item-subtitle>Auto-update apps at any time. Data charges may apply</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-action>
              <v-checkbox v-model="widgets"></v-checkbox>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Auto-add widgets</v-list-item-title>
              <v-list-item-subtitle>Automatically add home screen widgets</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-card>
    </v-dialog> -->


   <EdenLogo class="logo" />
    <v-spacer v-if="!IsshowOnMobile" />
    <!-- <div class="menu-area" v-if="!IsshowOnMobile" id="menu-section-area">
        <ul class="nav navbar-nav">
            <li class="item">
                <a href="#hero-section" class="page-scroll nav-link" data-scroll>Home</a>
            </li>
			<li class="item">
				<a href="#about-section" class="page-scroll nav-link" data-scroll>About</a>
			</li>
			<li class="item">
				<a href="#features-section" class="page-scroll nav-link" data-scroll>Features</a>
			</li>
			<li class="item">
				<a href="#distribution-section" class="page-scroll nav-link" data-scroll>Distribution</a>
			</li>
			<li class="item">
				<a href="#roadmap-section" class="page-scroll nav-link" data-scroll>Roadmap</a>
			</li>
			<li class="item">
				<a href="#faq-section" class="page-scroll nav-link" data-scroll>Faqs</a>
			</li>
			<li class="item">
              	<v-btn elevation="2" to='/wallet' class="btn-primary  btn-join-eden" >Join Eden</v-btn>
			</li>
		</ul>
     </div> -->
    
    </v-app-bar>
  
    <v-main id="hero-section">
      <Nuxt />
    </v-main>
 
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; Eden all Rights by Anonymous  {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>
<script>
import EdenLogo from "~/assets/images/logo_fit_dark.svg?inline";
export default {
  components: { EdenLogo },
  data () {
    return {
      dialog: false,
      notifications: false,
      sound: true,
      widgets: false,
      classTogglemenu: "close",
      isopenMenu:false,
      isopendrawer:false,
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'About',
          to: '#about-section'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Features',
          to: '#features-section'
        },
		{
          icon: 'mdi-chart-bubble',
          title: 'Distribution',
          to: '#distribution-section'
        },
		{
          icon: 'mdi-chart-bubble',
          title: 'Roadmap',
          to: '#roadmap-section'
        },
		{
          icon: 'mdi-chart-bubble',
          title: 'FAQs',
          to: '#faq-section'
        }],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Eden',
       
    }
  },
  computed: {
      IsshowOnMobile () {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs': return true
          case 'sm': return true
          case 'md': return true
          case 'lg': return false
          case 'xl': return false
        }
      },
    },
    methods: {
        menuClick: function (message) {
            var self = this;
            self.isopenMenu =!self.isopenMenu
            if(self.isopenMenu == true) {
                    self.classTogglemenu = "open"
                }else{
                    self.classTogglemenu = "close"
                }
        }
  }
}
</script>
