<template>
	<div class="feature-boxes-container container pt-2">
		<div class="row justify-content-center">
			<div
				class="col-sm-6 col-lg-4 appear-animate"
				data-animation-name="fadeInLeftShorter"
				data-animation-delay="500"
				data-animation-duration="1000"
				v-animate
			>
				<div class="feature-box feature-box-simple text-center">
					<i class="icon-earphones-alt"></i>

					<div class="feature-box-content p-0">
						<h3 class="text-capitalize">Customer Support</h3>
						<h5>Need Assistence?</h5>

						<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
					</div>
				</div>
			</div>

			<div
				class="col-sm-6 col-lg-4 appear-animate"
				data-animation-name="fadeInUpShorter"
				data-animation-delay="200"
				data-animation-duration="1000"
				v-animate
			>
				<div class="feature-box feature-box-simple text-center">
					<i class="icon-credit-card"></i>

					<div class="feature-box-content p-0">
						<h3 class="text-capitalize">Secure Payment</h3>
						<h5>Safe & Fast</h5>

						<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
					</div>
				</div>
			</div>

			<div
				class="col-sm-6 col-lg-4 appear-animate"
				data-animation-name="fadeInRightShorter"
				data-animation-delay="500"
				data-animation-duration="1000"
				v-animate
			>
				<div class="feature-box feature-box-simple text-center">
					<i class="icon-action-undo"></i>

					<div class="feature-box-content p-0">
						<h3 class="text-capitalize">Free Returns</h3>
						<h5>Easy & Free</h5>

						<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import { serviceSlider } from '~/utils/data/carousel'

export default {
	data: function () {
		return {
			serviceSlider: serviceSlider
		}
	}
}
</script>