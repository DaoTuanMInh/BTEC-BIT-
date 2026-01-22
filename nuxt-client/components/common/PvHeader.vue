<template>
	<header class="header">
		<div class="header-top">
			<div class="container">
				<div class="header-left d-none d-md-flex">
					<a
						href="tel:#"
						class="font-weight-bold text-primary d-flex align-items-center"
					><i class="sicon-phone"></i>(800)
						123-4567</a>
					<span class="separator"></span>
					<p><span class="font-weight-bold text-primary">Extra 15% OFF</span> Health & Wellness</p>
				</div>

				<div class="header-right header-dropdowns ml-0 ml-md-auto w-md-100">
					<div class="header-dropdown dropdown-expanded d-none d-xl-block">
						<a href="javascript:;">Links</a>
						<div class="header-menu">
							<ul>
								<li><a href="javascript:;">Track Your Order</a></li>
								<li><a
										href="javascript:;"
										class="login-link"
									>Help Center</a></li>
							</ul>
						</div>
					</div>

					<span class="separator d-none d-xl-block"></span>

					<div class="header-dropdown ">
						<a href="javascript:;">USD</a>
						<div class="header-menu">
							<ul>
								<li><a href="javascript:;">EUR</a></li>
								<li><a href="javascript:;">USD</a></li>
							</ul>
						</div>
					</div>

					<div class="header-dropdown mr-auto mr-sm-3 mr-md-0">
						<a href="javascript:;">ENG</a>
						<div class="header-menu">
							<ul>
								<li><a href="javascript:;">ENG</a>
								</li>
								<li><a href="javascript:;">FRA</a></li>
							</ul>
						</div>
					</div>

					<span class="separator"></span>

					<div class="social-icons ml-auto ml-md-0">
						<a
							href="javascript:;"
							class="social-icon social-facebook icon-facebook"
						></a>
						<a
							href="javascript:;"
							class="social-icon social-twitter icon-twitter"
						></a>
						<a
							href="javascript:;"
							class="social-icon social-instagram icon-instagram"
						></a>
					</div>
				</div>
			</div>
		</div>

		<div class="header-middle sticky-header">
			<div class="container">
				<div class="header-left col-lg-2 w-auto pl-0">
					<button
						class="mobile-menu-toggler"
						type="button"
						@click="showMobileMenu"
					>
						<i class="fas fa-bars"></i>
					</button>
					<nuxt-link
						to="/"
						class="logo"
					>
						<img
							src="~/static/images/home/logo.png"
							width="105"
							height="44"
							alt="Porto Logo"
						/>
					</nuxt-link>
				</div>

				<div class="header-right">
					<pv-main-menu></pv-main-menu>

					<pv-header-search></pv-header-search>

					<a
						href="javascript:;"
						@click="openLoginModal"
						class="header-icon header-icon-user"
						title="login"
					>
						<i class="icon-user-2"></i>
					</a>

					<nuxt-link
						to="/pages/wishlist"
						class="header-icon position-relative"
						title="wishlist"
					>
						<i class="icon-wishlist-2"></i>
						<span class="wishlist-count badge-circle">{{ wishList.length }}</span>
					</nuxt-link>

					<pv-cart-menu></pv-cart-menu>
				</div>
			</div>
		</div>
	</header>
</template>

<script>
import { mapGetters } from 'vuex';
import PvMainMenu from '~/components/common/partials/PvMainMenu';
import PvCartMenu from '~/components/common/partials/PvCartMenu';
import PvHeaderSearch from '~/components/common/partials/PvHeaderSearch';

document.querySelector( 'body' ).classList.add( 'loaded' );

export default {
	components: {
		PvMainMenu,
		PvCartMenu,
		PvHeaderSearch
	},
	computed: {
		...mapGetters( 'wishlist', [ 'wishList' ] )
	},
	methods: {
		openLoginModal: function () {
			this.$modal.show(
				() => import( '~/components/features/modal/PvLoginModal' ),
				{},
				{ width: '525', height: 'auto', adaptive: true }
			);
		},
		showMobileMenu: function () {
			document.querySelector( 'body' ).classList.add( 'mmenu-active' );
		},
		showMobileSearch: function ( e ) {
			let headerSearch = e.currentTarget.closest( '.header-search' );
			headerSearch.classList.add( 'show' );
			headerSearch
				.querySelector( '.header-search-wrapper' )
				.classList.add( 'show' );
		}
	}
};
</script>