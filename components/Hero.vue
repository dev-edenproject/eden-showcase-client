<template>
	<section id="hero-part" class="hero-area">
	    <div class="container">
            <v-row >
                <v-col cols="12" sm="5" md="5">
	                <div class="banner-detail">
						<h1 class="banner-title">
                            <span>Meta Eden </span> <br> Decentralize Metaverse
                        </h1>
                        <p class="sub-banner-title">
                            Real Decentralize Ecosystem
                            <br>
                             Next level of Ecosystem Cordination of Business and humanbeing
                        </p>
					
                        <div class="paper-hero-area">
                            <v-btn elevation="2" to='/wallet' class="btn-primary paper-btn" >White Paper</v-btn>
                            <div class="social-media-area">
                               
                                <a href="#" title="twitter"><Twitter class="icon-social" /></a>
                                 <a href="https://discord.gg/SGzhmzd9" title="discord">
                                <Discord class="icon-social" /></a>
                            </div>
                             
                        </div>
                        <div class="total-economy-area">
                            <div class="total-economy-detail-area">
                                <div class="total-economy-text-topic">
                                     Total economic wealth:
                                </div>
                                <div class="total-economy-text-value">
                                    100,000 usd
                                </div>
                            </div>
                            
                        </div>   
					</div>
                </v-col>
                <v-col cols="12" sm="1" md="1"></v-col>
                <v-col cols="12" sm="12" md="6" >
                    <div class="banner-main-img" v-if="!IsshowMobile">
						<div class="front-bg fadeInRight">
                            <HeroBanner class="hero-banner bounce-animation"/>
						</div>
					</div>
                </v-col>
            </v-row>
		</div>
	</section>
</template>

<script>
import HeroBanner from "~/assets/images/banner-img.svg?inline";
import Twitter from "~/assets/images/icons/twitter.svg";
import Discord from "~/assets/images/icons/icons8-discord.svg";

export default {
 components: { HeroBanner, Discord,Twitter },
 computed: {
      IsshowMobile () {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs': return true
          case 'sm': return true
          case 'md': return false
          case 'lg': return false
          case 'xl': return false
        }
      },
    },
}
</script>

