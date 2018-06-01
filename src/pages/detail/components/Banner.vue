<template>
	<div>
		<div class="banner" @click="handleBanerClick">
			<img src="http://img1.qunarzz.com/sight/p0/1603/33/337b483a8f5e76fb90.water.jpg_600x330_ec438400.jpg" alt="">
			<div class="banner-info">
				<div class="banner-title">
					sheiowhgoiwhfoi
				</div>
				<div class="banner-number">
					<span class="iconfont banner-icon">&#xe678;</span>39
				</div>
			</div>
		</div>
		<common-gallary 
			:imgs="imgs" 
			v-show="showGallary"
			@close="handleGallaryClose"
		></common-gallary>
	</div>
	
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
	export default {
		name: 'DetailBanner',
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
			CommonGallary
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