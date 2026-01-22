<template>
	<article class="post">
		<div class="post-box">
			<figure
				class="post-media"
				:class="post.type==='video'? 'post-video':''"
			>
				<nuxt-link
					:to="`/pages/single/${post.slug}`"
					v-if="post.type === 'image'"
				>
					<img
						v-lazy="`${baseUrl}${post.small_picture[0].url}`"
						alt="blog"
						:width="post.small_picture[0].width"
						:height="post.small_picture[0].height"
						v-if="post.small_picture.length > 0"
					/>
					<template v-else>
						<img
							v-lazy="`${baseUrl}${post.picture[0].url}`"
							alt="blog"
							:width="post.picture[0].width"
							:height="post.picture[0].height"
						/>
					</template>
				</nuxt-link>

				<template v-else-if="post.type === 'video'">
					<nuxt-link :to="`/pages/single/${post.slug}`">
						<img
							v-lazy="`${baseUrl}${post.picture[0].url}`"
							alt="blog"
							:width="post.picture[0].width"
							:height="post.picture[0].height"
						/>
					</nuxt-link>
					<a
						href="https://www.youtube.com/watch?v=vBPgmASQ1A0"
						@click.prevent="openVideoModal"
						class="btn-video btn-iframe"
					>
						<i class="far fa-play-circle"></i>
					</a>
				</template>

				<template v-else>
					<pv-carousel
						class
						:options="baseSlider1"
						v-if="post.small_picture.length > 0"
					>
						<img
							v-for="(img, index) in post.small_picture"
							v-lazy="`${baseUrl}${img.url}`"
							:key="'post-gallery' + index"
							:width="post.small_picture[0].width"
							:height="post.small_picture[0].height"
							class="swiper-slide"
							alt="post-gallery-image"
						/>
					</pv-carousel>
					<template v-else>
						<pv-carousel
							class
							:options="baseSlider1"
						>
							<img
								v-for="(img, index) in post.picture"
								v-lazy="`${baseUrl}${img.url}`"
								:key="'post-gallery' + index"
								:width="post.picture[0].width"
								:height="post.picture[0].height"
								class="swiper-slide"
								alt="post-gallery-image"
							/>
						</pv-carousel>
					</template>
				</template>

				<span
					class="prod-full-screen"
					@click="openLightBox"
				>
					<i class="fas fa-search"></i>
				</span>
			</figure>

			<div class="post-body">
				<div class="post-meta">
					<span class="meta-date">
						<i class="far fa-calendar-alt"></i>{{new Intl.DateTimeFormat('en-US',{month: 'long', day: 'numeric', 'year': 'numeric'}).format(date)}}</span>
					<span class="meta-author">
						<i class="far fa-user"></i>By <a
							href="#"
							title="Posts by John Doe"
							rel="author"
						>{{ post.author }}</a></span>
					<span class="meta-comments">
						<i class="far fa-comments"></i>
						<nuxt-link :to="'/pages/single/' + post.slug">{{ post.comments }} Comments</nuxt-link>
					</span>
				</div>

				<h2 class="post-title">
					<nuxt-link :to="'/pages/single/' + post.slug">{{ post.title }}</nuxt-link>
				</h2>

				<div
					class="post-content"
					v-if="isContent"
				>
					<p>{{ post.content }}</p>

					<nuxt-link
						:to="'/pages/single/' + post.slug"
						class="read-more"
					>read more...</nuxt-link>
				</div>
			</div>
		</div>
	</article>
</template>
<script>
import { baseUrl } from '~/api';
import { baseSlider1 } from '~/utils/data/carousel';
import PvCarousel from '~/components/features/PvCarousel';

export default {
	components: {
		PvCarousel
	},
	props: {
		post: Object,
		isContent: {
			type: Boolean,
			default: true
		},
		isAuthor: {
			type: Boolean,
			default: true
		},
		isMeta: {
			type: Boolean,
			default: true
		},
		postIndex: Number
	},
	data: function () {
		return {
			baseUrl: baseUrl,
			baseSlider1: baseSlider1
		};
	},
	computed: {
		date: function () {
			return new Date( this.post.date );
		}
	},
	methods: {
		openVideoModal: function () {
			this.$modal.show(
				() => import( '~/components/features/modal/PvVideoModal' ),
				{},
				{
					width: '880',
					height: '495',
					adaptive: true,
					class: 'video-modal-container'
				}
			);
		},
		openLightBox: function () {
			this.$parent.$parent.$parent.$refs.lightBox.showImage( this.postIndex );
		}
	}
};
</script>