<template>
	<section
		class="category-container curve-style bg-primary position-relative"
		:style="{'background-image': 'url(./images/home/banners/category-banner.jpg)'}"
	>
		<div
			class="container appear-animate"
			data-animation-name="fadeInUpShorter"
			data-animation-delay="200"
			v-animate
		>
			<div class="heading text-uppercase text-center">
				<h5 class="text-white">DEPARTMENTS</h5>
				<h2
					class="text-capitalize text-white mb-0 appear-animate"
					data-animation-delay="100"
					data-animation-name="fadeIn"
					v-animate
				>Browse Our Categories</h2>
			</div>

			<pv-carousel
				class="categories-slider swiper-carousel swiper-theme show-nav-hover nav-outer"
				:options="categorySlider"
			>
				<div
					class="product-category appear-animate swiper-slide"
					data-animation-name="fadeInUpShorter"
					v-animate
				>
					<nuxt-link :to="{path: '/shop', query: {category: 'gynecology'}}">
						<figure>
							<img
								:src="'./images/home/categories/category-1.jpg'"
								alt="category"
								width="280"
								height="240"
							/>
						</figure>
						<div class="category-content">
							<h3>Gynecology</h3>
						</div>
					</nuxt-link>
				</div>

				<div
					class="product-category appear-animate swiper-slide"
					data-animation-name="fadeInUpShorter"
					v-animate
				>
					<nuxt-link :to="{path: '/shop', query: {category: 'hepatology'}}">
						<figure>
							<img
								:src="'./images/home/categories/category-2.jpg'"
								alt="category"
								width="220"
								height="220"
							/>
						</figure>
						<div class="category-content">
							<h3>Hepatology</h3>
						</div>
					</nuxt-link>
				</div>

				<div
					class="product-category appear-animate swiper-slide"
					data-animation-name="fadeInUpShorter"
					v-animate
				>
					<nuxt-link :to="{path: '/shop', query: {category: 'respiratory'}}">
						<figure>
							<img
								:src="'./images/home/categories/category-3.jpg'"
								alt="category"
								width="220"
								height="220"
							/>
						</figure>
						<div class="category-content">
							<h3>Respiratory</h3>
						</div>
					</nuxt-link>
				</div>

				<div
					class="product-category appear-animate swiper-slide"
					data-animation-name="fadeInUpShorter"
					v-animate
				>
					<nuxt-link :to="{path: '/shop', query: {category: 'cardiology'}}">
						<figure>
							<img
								:src="'./images/home/categories/category-4.jpg'"
								alt="category"
								width="220"
								height="220"
							/>
						</figure>
						<div class="category-content">
							<h3>Cardiology</h3>
						</div>
					</nuxt-link>
				</div>

				<div
					class="product-category appear-animate swiper-slide"
					data-animation-name="fadeInUpShorter"
					v-animate
				>
					<nuxt-link :to="{path: '/shop', query: {category: 'gastroenterology'}}">
						<figure>
							<img
								:src="'./images/home/categories/category-6.jpg'"
								alt="category"
								width="220"
								height="220"
							/>
						</figure>
						<div class="category-content">
							<h3>Gastroenterology</h3>
						</div>
					</nuxt-link>
				</div>

				<div
					class="product-category appear-animate swiper-slide"
					data-animation-name="fadeInUpShorter"
					v-animate
				>
					<nuxt-link :to="{path: '/shop', query: {category: 'dental-care'}}">
						<figure>
							<img
								:src="'./images/home/categories/category-5.jpg'"
								alt="category"
								width="220"
								height="220"
							/>
						</figure>
						<div class="category-content">
							<h3>Dental Care</h3>
						</div>
					</nuxt-link>
				</div>

				<div
					class="product-category appear-animate swiper-slide"
					data-animation-name="fadeInUpShorter"
					v-animate
				>
					<nuxt-link :to="{path: '/shop', query: {category: 'respiratory'}}">
						<figure>
							<img
								:src="'./images/home/categories/category-3.jpg'"
								alt="category"
								width="220"
								height="220"
							/>
						</figure>
						<div class="category-content">
							<h3>Respiratory</h3>
						</div>
					</nuxt-link>
				</div>
			</pv-carousel>
		</div>
	</section>
</template>

<script>
import PvCarousel from '~/components/features/PvCarousel';
import { categorySlider } from '~/utils/data/carousel';

export default {
	components: {
		PvCarousel
	},
	data: function () {
		return {
			categorySlider: categorySlider
		}
	}
}
</script>