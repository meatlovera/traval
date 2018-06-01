<template>
	<div>
		<div class="banner" @click="handleBanerClick">
			<img :src="bannerImg" alt="">
			<div class="banner-info">
				<div class="banner-title">
					{{this.sightName}}
				</div>
				<div class="banner-number">
					<span class="iconfont banner-icon">&#xe678;</span>
					{{this.bannerImgs.length}}
				</div>
			</div>
		</div>
		<fade-animation>
			<common-gallary 
				:imgs="imgs" 
				v-show="showGallary"
				@close="handleGallaryClose"
			></common-gallary>
		</fade-animation>
	</div>
	
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
	export default {
		name: 'DetailBanner',
		props: {
			sightName: String,
			bannerImg: String,
			bannerImgs: Array
		},
		data () {
			return {
				showGallary: false,
				imgs: ['http://img1.qunarzz.com/sight/p0/1508/a5/4003f9dd7bebf61eccbf64046e26d487.water.jpg_350x240_e11745bd.jpg', 'http://img1.qunarzz.com/sight/p0/1501/ab/ab02fceb3fa0a60e.water.jpg_350x240_e7f0f154.jpg']
			}
		},
		methods: {
			handleBanerClick () {
				this.showGallary = true
			},
			handleGallaryClose () {
				this.showGallary = false
			}
		},
		components: {
			CommonGallary,
			FadeAnimation
		}
	};
</script>

<style lang="stylus" scoped>
	.banner
		position: relative
		overflow: hidden
		height: 0
		padding-bottom: 55%
		.banner-img
			width: 100%
		.banner-info
			display: flex
			position: absolute
			left: 0
			right: 0
			bottom: 0
			line-height: .6rem
			color: #fff
			background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
			.banner-title
				flex: 1
				font-size: .32rem
				padding: 0 .2rem
			.banner-number
				margin-top: .14rem
				padding: 0 .4rem
				line-height: .32rem
				height: .32rem
				border-radius: .2rem
				background: rgba(0, 0, 0, .8)
				font-size: .24rem
				.banner-icon
					font-size: .24rem
					margin-right: .1rem
</style>