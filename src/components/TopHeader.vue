<template>
	<div class="top-header">
		<div class="container">
			<a href="#" class="icon-mi"></a>
			<a href="#" class="pic-gif"></a>
			<div class="header-navs">
				<ul class="navs">
					<li v-for="item in navs" class="nav">
						<a href="#" class="nav-item">{{item['name']}}</a>
					</li>
				</ul>
			</div>
			<div class="header-search">
				<input class="search-ipt" type="search" name="search" value="">
				<label class="search-btn" for="search"></label>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data () {
		return {
			navs: [
				{'name': '小米手机'},
				{'name': '红米'},
				{'name': '平板 · 笔记本'},
				{'name': '电视'},
				{'name': '盒子 · 影音'},
				{'name': '路由器'},
				{'name': '智能硬件'},
				{'name': '服务'},
				{'name': '社区'}
			]
		}
	}
}
</script>

<style scoped>
.top-header {
	width: 100%;
	height: 100px;
}

.container {
	position: relative;
	display: flex;
	flex-flow: row;
	flex-wrap: nowrap;
	justify-content: flex-start;
	align-items: center;
	width: 1226px;
	height: 100%;
	margin: 0 auto;
}

.icon-mi {
	width: 55px;
	height: 55px;
	background: url('../assets/img/icon-mi.png') no-repeat;
	background-size: 100% 100%;
}

.pic-gif {
	width: 163px;
	height: 66px;
	margin-left: 10px;
	background: url('../assets/img/win.gif') no-repeat;
	background-size: 100% 100%;
}

.header-navs {
}
.navs {
	margin: 0;
	padding: 0;
	list-style: none;
	.nav {
		display: inline-block;
		a {
			font-size: 16px;
			padding: 0 10px;
			text-decoration: none;
			color: #333;
		}
	}
}

.header-search {
	position: absolute;
	top: 23px;
	right: 0;
	width: 295px;
	height: 50px;
	border: 1px solid #e0e0e0;
	.search-ipt {
		float: left;
		width: 240px;
		height: 100%;
		border: 0;
		outline: none;
	}
	.search-btn {
		display: block;
		float: right;
		width: 54px;
		height: 100%;
		border-left: 1px solid #e0e0e0;
	}
}
</style>
