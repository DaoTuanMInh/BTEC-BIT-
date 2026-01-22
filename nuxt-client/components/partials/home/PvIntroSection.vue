<template>
	<pv-carousel
		class="home-slider slide-animate show-nav-hover curve-style dot-inside mb-2 position-relative"
		:options="introSlider"
		v-animate
	>
		<div class="home-slide home-slide1 banner swiper-slide">
			<img
				class="swiper-lazy slide-bg"
				src="~/static/images/home/slider/slide-1.jpg"
				alt="slider image"
			>
			<div class="container d-flex align-items-center">
				<div
					class="banner-layer row align-items-center justify-content-center appear-animate mr-0 ml-0"
					data-animation-name="fadeInUpShorter"
					data-animation-delay="150"
					v-animate
				>
					<div class="col-lg-6 col-xl-6 col-md-12 p-0 content-left text-center text-md-left mb-6">
						<h4 class="text-transform-none">Shop for our products at exclusive prices</h4>
						<h3 class="text-transform-none">Infrared Thermometers</h3>
						<h2 class="text-uppercase">70% Off</h2>
						<nuxt-link
							to="/shop"
							class="btn btn-primary btn-lg appear-animate mr-0 ml-0"
							data-animation-name="fadeInUpShorter"
							data-animation-delay="200"
							v-animate
						>Shop Now!</nuxt-link>
					</div>
					<div
						class="col-md-6 col-xl-3 col-lg-3 col-sm-4 col-6 p-0 content-center appear-animate mr-0 ml-0"
						data-animation-name="fadeIn"
						data-animation-delay="700"
						v-animate
					>
						<p
							style="animation-delay: 800ms;"
							data-appear-animation="zoomIn"
							data-appear-animation-delay="800"
							class="appear-animation zoomIn appear-animation-visible"
							v-animate
						><img
								src="~/static/images/home/slider/thermometer.png"
								alt="thermometer"
								width="85"
								height="85"
								class="float-image"
							>
						</p>
					</div>
					<div
						class="col-lg-3 col-xl-3 col-md-12 col-sm-4 col-6 pr-0 content-right appear-animate mr-0 ml-0"
						data-animation-name="fadeInLeftShorter"
						data-animation-delay="280"
						v-animate
					>
						<img
							src="~/static/images/home/slider/fda.png"
							class="w-auto mb-3"
							alt="Slider Thumb"
						/>

						<ul class="text-capitalize">
							<li><i class="fa fa-check"></i>Non-Contact Temperature Taking</li>
							<li><i class="fa fa-check"></i>Get Readings in Only 1 Second</li>
							<li><i class="fa fa-check"></i>Fever Alarm at 100°F</li>
						</ul>

						<span class="d-block">from <span class="old-price">$299.99</span></span>
						<h5 class="d-inline-flex align-items-center mb-0">
							<span>to</span>
							<b class="coupon-sale-text text-white align-middle d-block"><sup>$</sup><em class="align-text-top">199</em><sup>99</sup></b>
						</h5>
					</div>
				</div>
			</div>
		</div>

		<div class="home-slide home-slide2 banner swiper-slide">
			<img
				class="swiper-lazy slide-bg"
				src="~/static/images/home/slider/slide-2.jpg"
				alt="slider image"
			>
			<div class="container d-flex align-items-center justify-content-center">
				<div
					class="banner-layer appear-animate mr-0 ml-0 "
					data-animation-name="fadeInUpShorter"
					data-animation-delay="150"
					v-animate
				>
					<h4 class="text-transform-none">Shop for our products at exclusive prices</h4>
					<h3 class="text-transform-none">Pro Respirator Mask</h3>
					<h2 class="text-uppercase">50% Off</h2>
					<nuxt-link
						to="/shop"
						class="btn btn-primary btn-lg appear-animate mr-0 ml-0"
						data-animation-name="fadeInUpShorter"
						data-animation-delay="200"
					>Shop Now!</nuxt-link>
				</div>
			</div>
		</div>
	</pv-carousel>
</template>

<script>
import PvCarousel from '~/components/features/PvCarousel';
import { introSlider } from '~/utils/data/carousel';

export default {
	components: {
		PvCarousel
	},
	data: function () {
		return {
			introSlider: introSlider
		};
	},
	mounted: function () {
		window.addEventListener( 'scroll', this.floatHandler, { passive: true } );
	},
	destroyed: function () {
		window.removeEventListener( 'scroll', this.floatHandler, { passive: true } );
	},
	methods: {
		floatHandler: function () {
			document.querySelectorAll( '.float-image' ).forEach( item => {
				let element = item.parentNode;
				let yPos, parallaxSpeed = 1;
				let offsetTop = element.closest( '.swiper-carousel' ).offsetTop;
				yPos = ( offsetTop - window.pageYOffset ) * 5 * parallaxSpeed / offsetTop;

				item.setAttribute( 'style', "transform: translate3d(0," + yPos + "%,0)" );
			} )
		}
	}
};
</script>