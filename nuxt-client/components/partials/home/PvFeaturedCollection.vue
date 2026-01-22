<template>
	<section class="products-container feautured-container">
		<div class="container">
			<div class="heading text-uppercase text-center">
				<h5
					class="appear-animate"
					data-animation-name="fadeInUpShorter"
					data-animation-delay="200"
					v-animate
				>
					EXCLUSIVE SELECTION</h5>
				<h2
					class="text-capitalize mb-0 appear-animate"
					data-animation-delay="300"
					data-animation-name="fadeInUpShorter"
					v-animate
				>Featured
					Products</h2>
			</div>

			<pv-carousel
				class="products-slider custom-products nav-outer show-nav-hover nav-image-center"
				:options="baseSlider3"
				v-if="products.length === 0"
			>
				<div
					class="product-loading-overlay swiper-slide"
					v-for="number in [1,2,3,4,5]"
					:key="'new-skel-' + number"
				>
				</div>
			</pv-carousel>

			<pv-carousel
				class="products-slider custom-products nav-outer show-nav-hover nav-image-center"
				:options="baseSlider3"
				v-if="products.length > 0"
			>
				<pv-product-one
					v-for="(product,index) in products.slice(0,5)"
					:key="'new' + index"
					:product="product"
					class="swiper-slide"
				></pv-product-one>
			</pv-carousel>

			<div
				class="banner banner-big-sale mb-6 appear-animate"
				data-animation-delay="100"
				data-animation-name="fadeIn"
				v-animate
				:style="{'background': '#2A95CB center/cover url(./images/home/banners/banner.jpg)'}"
			>
				<div class="banner-content row align-items-center mx-0">
					<div class="col-lg-8 col-md-9 d-flex justify-content-center justify-content-md-start flex-column flex-md-row">
						<h2
							class="text-dark text-uppercase text-center text-md-left ls-n-20 mb-md-0 px-md-4 appear-animate"
							data-animation-name="fadeInLeftShorter"
							data-animation-delay="200"
							v-animate
						>
							<b class="text-white d-inline-block mb-1 mb-md-0">Big Sale</b>
						</h2>

						<h3
							class="text-center text-md-left appear-animate"
							data-animation-name="fadeInLeftShorter"
							data-animation-delay="200"
							v-animate
						>
							Delivering Covid19 Essentials
							<small class="d-block text-transform-none align-middle">HAND SANITIZER,
								INFRARED THERMOMETERS AND MORE…</small>
						</h3>
					</div>
					<div class="col-lg-4 col-md-3 text-center text-md-left text-lg-right mt-2 mt-lg-0">
						<nuxt-link
							class="btn btn-light btn-primary btn-lg appear-animate"
							data-animation-name="fadeIn"
							data-animation-delay="150"
							v-animate
							to="/shop"
						>Shop Now</nuxt-link>
					</div>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
import PvCarousel from '~/components/features/PvCarousel';
import PvProductOne from '~/components/features/product/PvProductOne';
import { baseSlider3 } from '~/utils/data/carousel';

export default {
	components: {
		PvCarousel,
		PvProductOne
	},
	props: {
		products: Array
	},
	data: function () {
		return {
			baseSlider3: baseSlider3
		};
	}
};
</script>