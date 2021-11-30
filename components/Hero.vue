<template>
	<section id="hero-part" class="hero-area">
	    <div class="container">
            <v-row >
                <v-col cols="12" sm="5" md="5">
	                <div class="banner-detail">
						<h1 class="banner-title">
                            <span>Discover the new </span> <br> ecosystem
                        </h1>
						<p class="sub-banner-title">The society world are freedom & fair return</p>
                        <div class="paper-hero-area">
                            <v-btn elevation="2" to='/wallet' class="btn-primary" >White Paper</v-btn>
                        </div>
                        <div class="total-economy-area">
                            <h6>TOTAL ECONOMY WEALTH</h6>
                            <div class="total-economy-detail-area">
                                <div class="total-economy-text-topic">
                                     Cypto Asset:
                                </div>
                                <div class="total-economy-text-value">
                                    100,000$
                                </div>
                            </div>
                            <div class="total-economy-detail-area">
                                <div class="total-economy-text-topic">
                                    Real Sector Currency:
                                </div>
                                <div class="total-economy-text-value">
                                    230,000$
                                </div>
                            </div>
                            <div class="total-economy-detail-area">
                                <div class="total-economy-text-topic">
                                    Real Sector Asset:
                                </div>
                                <div class="total-economy-text-value">
                                    350,000$
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

export default {
 components: { HeroBanner },
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

