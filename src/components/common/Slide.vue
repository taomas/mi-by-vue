<template>
	<div class="banner">
		<span class="slide-pre"></span>
		<span class="slide-next"></span>
		<div class="slide active">
			<img src="http://i3.mifile.cn/a4/ef9c4e97-2971-495c-987d-bd3f3b1b7b58" alt="" />
		</div>
		<div class="slide">
			<img src="http://i3.mifile.cn/a4/3c788170-183e-4f26-b00b-6ef1b743906c" alt="" />
		</div>
		<div class="slide">
			<img src="http://i3.mifile.cn/a4/67c4e203-f46b-4e58-8da2-859d69c313fb" alt="" />
		</div>
	</div>
</template>

<script>
export default {
	methods: {
		slideNext () {
		}
	}
}
</script>

<style scoped>
.banner {
	position: relative;
	width: 1226px;
	height: 462px;
	z-index: 0;
}

.slide-pre {
	display: block;
	position: absolute;
	left: 235px;
	top: 50%;
	width: 40px;
	height: 70px;
	margin-top: -35px;
	background: #ccc;
	z-index: 10;
	cursor: pointer;
}

.slide-next {
	display: block;
	position: absolute;
	right: 0;
	top: 50%;
	width: 40px;
	height: 70px;
	margin-top: -35px;
	background: #ccc;
	z-index: 10;
	cursor: pointer;
}

.slide {
	display: none;
	position: absolute;
	left: 0;
	top: 0;
	width: 100%;
	height: 100%;
	transition: 0.4s ease-in-out transform, opacity;
}

.active {
	display: block;
}
</style>
