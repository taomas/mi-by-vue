<template>
	<div class="footer-wrap">
		<div class="footer">
			<div class="footer-service">
				<ul class="service clearfix">
					<li class="service-item">
						<span class="icon"><i class="fa fa-gavel"></i></span>
						1小时快修服务
					</li>
					<li class="service-item">
						<span class="icon"><i class="fa fa-history"></i></span>
						7天无条件退货
					</li>
					<li class="service-item">
						<span class="icon"><i class="fa fa-history"></i></span>
						15天免费换货
					</li>
					<li class="service-item">
						<span class="icon"><i class="fa fa-gift"></i></span>
						满150元包邮
					</li>
					<li class="service-item">
						<span class="icon"><i class="fa fa-location-arrow"></i></span>
						520余家售后网点
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data () {
		return {
			service: [{
			}]
		}
	}
}
</script>

<style>
.footer {
	width: 1226px;
	height: auto;
	margin: 0 auto;
	padding-bottom: 50px;
}

.footer-service {
	padding: 27px 0;
}
.service {
	.service-item {
		float: left;
		width: 245px;
		height: 27px;
		line-height: 27px;
		font-size: 16px;
		color: #616161;
		.icon {
			display: inline-block;
			height: 27px;
			line-height: 27px;
			font-size: 24px;
		}
	}
}
</style>
