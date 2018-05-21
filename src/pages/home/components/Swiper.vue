<template>
	<div class="wrapper">
		<swiper :options="swiperOption">
	    <!-- slides -->
	    <swiper-slide v-for="item of swiperList" :key="item.id">
	    	<img class="swiper-img" :src="item.imgUrl" alt="">
	    </swiper-slide>
	    <!-- Optional controls -->
	    <div class="swiper-pagination"  slot="pagination"></div>
	  </swiper>
	</div>
	
</template>

<script>
	export default {
		name: 'HomeSwiper',
		data () {
			return{
				swiperOption: {
					pagination: '.swiper-pagination',
					loop: true,
					autoplay: 4000,
				},
				swiperList: [{
					id: '0001',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/e5/59fad13a64807d02.jpg_750x200_713ae984.jpg'
				},{
					id: '0002',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/5c/969bfa7af00a2702.jpg_750x200_b99b8e07.jpg'
				}]	
			}
		}
	};
</script>

<style lang="stylus" scoped>
	.wrapper >>> .swiper-pagination-bullet-active
			background: #fff 
	.wrapper
		width: 100%
		height: 0
		padding-bottom: 26.67%
		background: #eee
		.swiper-img
			width: 100%
</style>