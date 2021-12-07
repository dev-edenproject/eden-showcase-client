<template>
	<section id="hero-part" class="hero-area">
	    <div class="left-hero-area">
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
                            <v-btn to='/wallet' class="btn-primary paper-btn" >White Paper</v-btn>
                            <div class="social-media-area">
                               
                                <a href="#" title="twitter"><Twitter class="icon-social" /></a>
                                 <a href="https://discord.gg/SGzhmzd9" title="discord">
                                <Discord class="icon-social" /></a>
                            </div>
                             
                        </div>
                        <div class="total-economy-area" :class="classToggleWealth">
                            <div class="total-economy-detail-area">
                                <div class="right-area">
                                     <a class="btn-toggle-total-economy" v-on:click="totalWealthClick()" >
                                        <EdenLogo style="width:20px;" />
                                        <span>Economic Wealth</span>
                                        <v-icon color="#00fdff">
                                            mdi-chevron-right
                                        </v-icon>
                                    </a>
                                </div>
                                <div class="left-area">
                                    <div class="wrapper">
                                        <div class="economic-info-shadow">Economic info</div>
                                    </div>
                                    <div class="wealth-detail">
                                        <div class="wealth-detail-left-area">
                                            <div class="total-economy-text-topic">Total economic wealth</div>
                                            <h6 class="total-economy-text-value">  0 $ </h6>
                                        </div>
                                        <div class="wealth-detail-right-area">
                                             <EdenLogo style="width:100px;" />
                                        </div>
                                    </div>
                                  
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
import EdenLogo from "~/assets/images/logo_fit_dark.svg?inline";

export default {
 components: { HeroBanner, Discord,Twitter,EdenLogo },
 data () {
    return {
       classToggleWealth: "total-economy-close",
       isWealthOpen:false
    }
  },
 computed: {
      IsshowMobile () {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs': return true
          case 'sm': return true
          case 'md': return false
          case 'lg': return false
          case 'xl': return false
        }
      }
    },
    methods: {
        totalWealthClick: function (message) {
            var self = this;
            self.isWealthOpen =!self.isWealthOpen
            if(self.isWealthOpen == true) {
                    self.classToggleWealth = "total-economy-open"
                }else{
                    self.classToggleWealth = "total-economy-close"
                }
        }
  }
}
</script>

