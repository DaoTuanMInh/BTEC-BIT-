<template>
	<footer class="footer bg-dark">
		<div class="footer-middle">
			<div class="container">
				<div class="row">
					<div class="col-md-12 col-xl-2 col-lg-2 d-flex align-items-center">
						<nuxt-link to="/">
							<img
								src="~/static/images/home/footer-logo.png"
								alt="Logo"
								class="logo-footer"
							>
						</nuxt-link>
					</div>

					<div class="col-md-12 col-xl-3 col-lg-3">
						<div class="widget">
							<h4 class="widget-title">GET IN TOUCH</h4>
							<ul class="contact-info">
								<li>
									<span class="contact-info-label">Address</span>123 Street Name, City, England
								</li>
								<li>
									<span class="contact-info-label">Phone</span><a href="tel:">Toll Free (123)
										456-7890</a>
								</li>
								<li>
									<span class="contact-info-label">Email</span> <a href="mailto:mail@example.com">mail@example.com</a>
								</li>
								<li>
									<span class="contact-info-label">Working Days/Hours</span>
									Mon - Sun / 9:00AM - 8:00PM
								</li>
							</ul>

							<div class="social-icons">
								<a
									href="javascript:;"
									class="social-icon social-instagram icon-instagram"
									title="Instagram"
								></a>
								<a
									href="javascript:;"
									class="social-icon social-twitter icon-twitter"
									title="Twitter"
								></a>
								<a
									href="javascript:;"
									class="social-icon social-facebook icon-facebook"
									title="Facebook"
								></a>
							</div>
						</div>
					</div>

					<div class="col-md-6 col-xl-3 col-lg-3 col-12">
						<div class="widget">
							<h4 class="widget-title">Customer Services</h4>

							<ul class="links">
								<li><a href="javascript:;">Help & FAQs</a></li>
								<li><a href="javascript:;">Order Tracking</a></li>
								<li><a href="javascript:;">Shipping & Delivery</a></li>
								<li><a href="javascript:;">Orders History</a></li>
								<li><a href="javascript:;">Advanced Search</a></li>
								<li>
									<nuxt-link to="/pages/login">Login</nuxt-link>
								</li>
								<li><a href="javascript:;">Careers</a></li>
								<li>
									<nuxt-link to="/pages/about-us">About Us</nuxt-link>
								</li>
								<li><a href="javascript:;">Corporate Sales</a></li>
								<li><a href="javascript:;">Careers</a></li>
							</ul>
						</div>
					</div>

					<div class="col-md-6 col-xl-4 col-lg-4 col-12">
						<div class="widget widget-newsletter">
							<h4 class="widget-title ls-n-10">Subscribe newsletter</h4>
							<p>Get all the latest information on events,<br /> sales and offers. Sign up for
								newsletter:
							</p>
							<form
								action="#"
								class="mb-0"
							>
								<input
									type="email"
									class="form-control m-b-3"
									placeholder="Email address"
									required
								>

								<input
									type="submit"
									class="btn btn-outline-primary shadow-none"
									value="Subscribe"
								>
							</form>
						</div>
					</div>
				</div>
			</div>
		</div>

		<div class="container">
			<div class="footer-bottom">
				<div class="container d-sm-flex align-items-center">
					<div class="footer-left">
						<span class="footer-copyright">Porto Medical. © <span class="d-inline-block">2021.</span>
							All Rights Reserved
						</span>
					</div>

					<div class="footer-right ml-auto mt-1 mt-sm-0">
						<div class="payment-icons">
							<span
								class="payment-icon visa"
								:style="{'background-image': 'url(./images/payments/payment-visa.svg)'}"
							></span>
							<span
								class="payment-icon paypal"
								:style="{'background-image': 'url(./images/payments/payment-paypal.svg)'}"
							></span>
							<span
								class="payment-icon stripe"
								:style="{'background-image': 'url(./images/payments/payment-stripe.png)'}"
							></span>
							<span
								class="payment-icon verisign"
								:style="{'background-image':  'url(./images/payments/payment-verisign.svg)'}"
							></span>
						</div>
					</div>
				</div>
			</div>
		</div>
	</footer>
</template>