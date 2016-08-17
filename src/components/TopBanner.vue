<template>
	<div class="top-banner clearfix">
		<div class="site-category">
			<ul class="side-left">
				<li class="side-item" v-for="item in sideItems">
					{{item}}
				</li>
			</ul>
		</div>
		<slide></slide>
		<!-- <div class="site-banner">
			<a href="#" class="slide"></a>
		</div> -->
	</div>
</template>

<script>
import slide from './common/Slide.vue'
export default {
	data () {
		return {
			sideItems: ['手机 电话卡', '笔记本 平板', '电视 盒子', '路由器 智能硬件', '移动电源 电池 插线板', '耳机 音响', '保护套 贴膜', '线材 支架 存储卡', '箱包 服饰', '兔米 生活周边'],
			banners: [
				{sourcePath: 'http://i3.mifile.cn/a4/ef9c4e97-2971-495c-987d-bd3f3b1b7b58'},
				{sourcePath: 'http://i3.mifile.cn/a4/3c788170-183e-4f26-b00b-6ef1b743906c'},
				{sourcePath: 'http://i3.mifile.cn/a4/67c4e203-f46b-4e58-8da2-859d69c313fb'},
				{sourcePath: 'http://i3.mifile.cn/a4/709b3551-c643-498c-8dcd-2572baa56bd6'},
				{sourcePath: 'http://i3.mifile.cn/a4/dab07ffc-8853-4b2f-9a90-da297c98d6d3'}
			]
		}
	},
	components: {
		slide
	}
}
</script>

<style scoped>
.top-banner {
	position: relative;
	width: 1226px;
	height: auto;
	margin: 0 auto;
}
.site-category {
	position: absolute;
	left: 0;
	top: 0;
	width: 235px;
	height: auto;
	padding: 20px 0;
	background: rgba(0, 0, 0, 0.3);
	z-index: 11;
}
.side-left {
	margin: 0;
	padding: 0;
	width: 235px;
	height: 420px;
	list-style: none;
	.side-item {
		width: 100%;
		height: 42px;
		line-height: 42px;
		color: #fff;
		text-align: center;
		cursor: pointer;
		&:hover {
			background: #ff6700;
		}
	}
}
.slide {

}
</style>
