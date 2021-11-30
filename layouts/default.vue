<template>
  <v-app>
 
  	<v-navigation-drawer v-if="drawer" v-model="drawer" :mini-variant="miniVariant" :clipped="clipped"
      fixed
      app
    >
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
           <v-btn elevation="2" to='/wallet' class="btn-primary" >Join Eden</v-btn>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" class="header-area"  fixed app >
    
   <EdenLogo class="logo" />
    <v-spacer v-if="!IsshowOnMobile" />
    <div class="menu-area" v-if="!IsshowOnMobile" id="menu-section-area">
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
              	<v-btn elevation="2" to='/wallet' class="btn-primary" >Join Eden</v-btn>
			</li>
		</ul>
     </div>
    <v-app-bar-nav-icon v-if="IsshowOnMobile" @click.stop="drawer = !drawer" />
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
import EdenLogo from "~/assets/images/logo_fit_light.svg?inline";
export default {
  components: { EdenLogo },
  data () {
    return {
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
}
</script>
