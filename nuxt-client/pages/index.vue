<template>
	<main class="main home-page">
		<pv-intro-section></pv-intro-section>

		<pv-service-section></pv-service-section>

		<pv-featured-collection :products="featuredProducts"></pv-featured-collection>

		<pv-new-collection :products="newProducts"></pv-new-collection>

		<pv-category-section></pv-category-section>

		<div class="container">
			<pv-small-collection
				:featured-products="featuredProducts.slice(0,3)"
				:best-products="bestProducts.slice(0,3)"
				:latest-products="newProducts.slice(0,3)"
				:top-rated-products="topRatedProducts.slice(0,3)"
			></pv-small-collection>

			<hr class="mt-4 m-b-5">

			<pv-blog-section :posts="posts"></pv-blog-section>

			<hr class="mt-4 mb-0">

			<pv-brand-section></pv-brand-section>
		</div>

		<light-box
			v-if="lightBoxMedia.length > 0"
			ref="lightBox"
			:media="lightBoxMedia"
			:show-light-box="false"
			class="blog-light-box"
		/>
	</main>
</template>

<script>
import LightBox from 'vue-image-lightbox';
import PvIntroSection from '~/components/partials/home/PvIntroSection';
import PvServiceSection from '~/components/partials/home/PvServiceSection';
import PvCategorySection from '~/components/partials/home/PvCategorySection';
import PvNewCollection from '~/components/partials/home/PvNewCollection';
import PvSmallCollection from '~/components/partials/product/PvSmallCollection';
import PvBlogSection from '~/components/partials/home/PvBlogSection';
import PvBrandSection from '~/components/partials/home/PvBrandSection';
import PvFeaturedCollection from '~/components/partials/home/PvFeaturedCollection';

import {
	getProductsByAttri,
	getTopSellingProducts,
	getTopRatedProducts
} from '~/utils/service';
import { getCookie } from '~/utils';
import Api, { baseUrl } from '~/api';

export default {
	components: {
		LightBox,
		PvIntroSection,
		PvServiceSection,
		PvCategorySection,
		PvNewCollection,
		PvSmallCollection,
		PvBlogSection,
		PvBrandSection,
		PvFeaturedCollection
	},
	data: function () {
		return {
			products: [],
			posts: [],
			featuredProducts: [],
			newProducts: [],
			bestProducts: [],
			topRatedProducts: [],
			timerId: 0
		};
	},
	computed: {
		lightBoxMedia: function () {
			let pictures = [];
			for ( let i = 0; i < this.posts.length; i++ ) {
				pictures.push( this.posts[ i ].picture[ 0 ] );
			}
			return pictures.reduce( ( acc, cur ) => {
				return [
					...acc,
					{
						src: `${ baseUrl }${ cur.url }`,
						thumb: `${ baseUrl }${ cur.url }`
					}
				];
			}, [] );
		}
	},
	mounted: function () {
		Api.get( `${ baseUrl }/demo38` )
			.then( response => {
				this.products = response.data.products;
				this.posts = response.data.posts;
				this.featuredProducts = getProductsByAttri(
					response.data.products
				);
				this.newProducts = getProductsByAttri(
					response.data.products,
					'is_new'
				);
				this.bestProducts = getTopSellingProducts(
					response.data.products
				);
				this.topRatedProducts = getTopRatedProducts(
					response.data.products
				);
			} )
			.catch( error => ( { error: JSON.stringify( error ) } ) );

		this.timerId = setTimeout( () => {
			if (
				this.$route.path === '/' &&
				getCookie( 'newsletter' ) !== 'false'
			) {
				this.$modal.show(
					() =>
						import( '~/components/features/modal/PvNewsletterModal' ),
					{},
					{ width: '740', height: 'auto', adaptive: true, class: 'newsletter-modal' }
				);
			}
		}, 10000 );
	},
	destroyed: function () {
		clearTimeout( this.timerId );
	}
};
</script>