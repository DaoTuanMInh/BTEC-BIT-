<template>
	<div
		class="blog-section media-with-zoom appear-animate"
		data-animation-name="fadeInUpShorter"
		data-animation-delay="250"
		v-animate
	>
		<div class="heading text-uppercase text-center">
			<h5>OUR BLOG</h5>
			<h2
				class="text-transform-none mb-0 appear-animate"
				data-animation-delay="100"
				data-animation-name="fadeIn"
				v-animate
			>Recent Articles and News</h2>
			<p class="text-transform-none">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed
				imperdiet libero idnisl euis</p>
		</div>

		<pv-carousel
			class="post-slider swiper-carousel swiper-theme mb-0"
			:options="blogSlider"
		>
			<div
				class="swiper-slide"
				v-for="(post,index) in posts"
				:key="'blog-' + index"
			>
				<pv-post-four
					:post="post"
					:post-index="index"
				></pv-post-four>
			</div>
		</pv-carousel>
	</div>
</template>

<script>
import PvCarousel from '~/components/features/PvCarousel';
import PvPostFour from '~/components/features/post/PvPostFour';
import PvBrandSection from '~/components/partials/home/PvBrandSection';
import { blogSlider } from '~/utils/data/carousel';

export default {
	components: {
		PvCarousel,
		PvPostFour,
		PvBrandSection
	},
	props: {
		posts: Array
	},
	data: function () {
		return {
			blogSlider: blogSlider
		}
	}
}
</script>