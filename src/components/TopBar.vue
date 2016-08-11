<template>
  <div class="top-container">
		<div class="top-bar clearfix">
			<div class="topbar-nav">
				<ul class="nav-wrap">
					<li v-for="item in navs" class="nav">
						<a href="#" class="nav-name">{{item['name']}}</a>
						<span class="nav-separate" v-show="$index !== 8">|</span>
					</li>
				</ul>
			</div>
			<div class="topbar-info">
				<a href="#">登陆</a>
				<span class="nav-separate" v-show="$index !== 8">|</span>
				<a href="#">注册</a>
			</div>
			<div class="topbar-cart">
				<a href="#">购物车<span>0<span></a>
			</div>
		</div>
  </div>
</template>

<script>
export default {
	data: function () {
		return {
			navs: [
				{'name': '小米商城'},
				{'name': 'MIUI'},
				{'name': '米聊'},
				{'name': '游戏'},
				{'name': '多看阅读'},
				{'name': '云服务'},
				{'name': '小米网移动版'},
				{'name': '问题反馈'},
				{'name': 'Select Region'}
			]
		}
	},
	methods: {

	},
	components: {
	// Hello
	}
}
</script>

<style scoped>

.top-container {
	width: 100%;
	height: 40px;
	background: #333;
}

.top-bar {
	width: 1226px;
	margin: 0 auto;
}

.topbar-nav {
	float: left;
	display: inline-block;
	height: 40px;
	line-height: 40px;
	overflow: hidden;
}

.nav-wrap {
	display: inline-block;
	margin: 0;
	padding: 0;
	list-style: none;
	.nav {
		display: inline-block;
		text-decoration: none;
		height: 40px;
		line-height: 40px;
		padding-left: 10px;
		& :hover {
			color: #fff;
		}
		& a {
			display: inline-block;
			font-size: 12px;
			color: #b0b0b0;
			text-decoration: none;
		}
	}
}
</style>
