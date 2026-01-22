<template>
	<section class="products-container new-products-container">
		<div class="container">
			<div class="heading text-uppercase text-center">
				<h5
					class="appear-animate"
					data-animation-name="fadeInUpShorter"
					data-animation-delay="200"
					v-animate
				>
					RECENTLY ARRIVED</h5>
				<h2
					class="text-capitalize mb-0 appear-animate"
					data-animation-delay="300"
					data-animation-name="fadeInUpShorter"
					v-animate
				>New Arrivals</h2>
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