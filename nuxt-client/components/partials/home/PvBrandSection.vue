<template>
	<div
		class="partners-container appear-animate"
		data-animation-name="fadeInUpShorter"
		data-animation-delay="250"
		v-animate
	>
		<pv-carousel
			class="appear-animate"
			data-animation-name="fadeIn"
			data-animation-delay="100"
			:options="brandSlider"
			v-animate
		>
			<div class="swiper-slide">
				<img
					src="~/static/images/home/logos/logo1.png"
					alt="logo image"
					width="107"
					height="75"
				>
			</div>

			<div class="swiper-slide">
				<img
					src="~/static/images/home/logos/logo2.png"
					alt="logo image"
					width="107"
					height="75"
				>
			</div>

			<div class="swiper-slide">
				<img
					src="~/static/images/home/logos/logo3.png"
					alt="logo image"
					width="107"
					height="75"
				>
			</div>

			<div class="swiper-slide">
				<img
					src="~/static/images/home/logos/logo4.png"
					alt="logo image"
					width="107"
					height="75"
				>
			</div>

			<div class="swiper-slide">
				<img
					src="~/static/images/home/logos/logo5.png"
					alt="logo image"
					width="107"
					height="75"
				>
			</div>

			<div class="swiper-slide">
				<img
					src="~/static/images/home/logos/logo6.png"
					alt="logo image"
					width="107"
					height="75"
				>
			</div>
		</pv-carousel>
	</div>
</template>

<script>
import PvCarousel from '~/components/features/PvCarousel';
import { brandSlider } from '~/utils/data/carousel';

export default {
	components: {
		PvCarousel
	},
	data: function () {
		return {
			brandSlider: brandSlider
		}
	}
}
</script>