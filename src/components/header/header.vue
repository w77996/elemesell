<template>
	<div class="header">
		<div class="content-wrapper">
			<div class="avatar">
				<img width="64" height="64" :src="seller.avatar">
			</div>
			<div class="content">
				<div class="title">
					<span class="brand"></span>
					<span class="name">{{seller.name}}</span>
				</div>
				<div class="description">
				{{seller.description}}/{{seller.deliveryTime}}分钟送达
				</div>
				<div v-if="seller.supports" class="support">
					<span class="icon" :class="classMap[seller.supports[0].type]"></span>
					<span class="text">{{seller.supports[0].description}}</span>
				</div>
			</div>
			<div v-if="seller.supports" class="support-count">
				<span class="count">{{seller.supports.length}}个</span>
				<i class="icon-zuoyoujiantou"></i>
			</div>
		</div>
		<div class="bulletin-wrapper">
			<span class="bulletin-title"></span>
			<span class="bulletin-text">{{seller.bulletin}}</span>
			<i class="icon-zuoyoujiantou"></i>
		</div> 
		
	</div>

</template>
<script type="text/ecmascript-6">
export default {
props: {
seller: {
type: Object
}
},
created() {
this.classMap = ['decrease', 'discount', 'special', 'invoice', 'guarantee'];
}
};
</script>

<style lang="stylus" rel="stylesheet/stylus">

@import "../../common/stylus/mixin"

.header
	
	color: #fff
	overflow hidden
	background: rgba(7, 17, 27, 0.5)
	.content-wrapper
		position: relative
		padding: 24px 12px 18px 24px
		font-size: 0
		.avatar
			display: inline-block
			vertical-align: top
			img
				border-radius: 2px
		.content
			display: inline-block
			margin-left:16px
			font-size: 14px
			.title
				margin: 2px 0 8px 0
				.brand
					display: inline-block
					vertical-align: top
					width: 30px
					height: 18px
					bg-image('brand')
					background-size:30px 18px
					background-repeat: no-repeat
				.name
					margin-left: 6px
					font-size: 16px
					line-height: 18px
					font-weight: bold
			.description
				margin-bottom: 10px
				line-height: 12px
				font-size: 12px
			.support
				.icon
					display: inline-block
					width: 12px
					height: 12px
					margin-right: 4px
					vertical-align: top
					background-size: 12px 12px
					background-repeat: no-repeat
					&.decrease
						bg-image('decrease_1')
					&.discount
						bg-image('discount_1')
					&.guarantee
						bg-image('guarantee_1')
					&.invoice
						bg-image('invoice_1')
					&.special
						bg-image('special_1')
				.text
					line-height: 12px
	          		font-size: 12px
        .support-count
        	position: absolute
        	right: 12px
        	bottom: 18px
        	padding: 0 8px
        	height: 24px
        	line-height: 90px
        	border-radius: 12px
        	background: rgba(0, 0, 0, 0.2)
        	text-align: center
        	.count
        		vertical-align: top
        		font-size: 10px
        	.icon-zuoyoujiantou
        		margin-left: 2px
		        line-height: 24px
		        font-size: 10px
	.bulletin-wrapper
	    position: relative
	    background-color: rgba(7, 17, 27, 0.2)
	    height: 28px
	    line-height: 28px
	    padding: 0 22px 0 12px
	    white-space: normal
	    overflow: hidden
	    text-overflow: ellipsis
        .bulletin-title
	    	display: inline-block
	    	height: 12px
	    	width: 22px
	    	bg-image('bulletin')
	    	background-size: 22px 12px
	    	background-repeat: no-repeat
	    .bulletin-text
	    	vertical-align: top
		    margin: 0 4px
		    font-size: 10px
		.icon-zuoyoujiantou
			position absolute
		    font-size 20px
		    right 12px
		    top: 0px


    
    			 


</style>

