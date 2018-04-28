<template>
	<div id="home">
		<div :class="{menu:true, hideIcon:asideMenuFlag}">
			<i class="el-icon-menu" @click="showMenu"></i>
		</div>
		<!-- 右侧菜单 -->
		<div :class="{asideMenu:true, clearfix:true, hideMenu:!asideMenuFlag}">
			<div class="left fl">
				<i class="el-icon-close" @click="hideMenu"></i>
			</div>
			<div class="right fr">
				<h3 class="title">MENU</h3>
				<ul class="info">
					<li>选项1</li>
					<li>选项2</li>
					<li>选项3</li>
					<li>选项4</li>
				</ul>
			</div>
		</div>
		<header class="header">
			<img src="/static/imgs/banner01.jpg" alt="">
		</header>
		<footer class="footer">
			<div class="info w">
				<h3 class="title">FOLLOW</h3>
				<div>
					<i class="iconfont icon-github"></i>
					<i class="iconfont icon-email"></i>
					<i class="iconfont icon-weibo"></i>
				</div>
			</div>
		</footer>
		<div class="mark" v-show="markFlag"></div>
	</div>
</template>

<script>
	export default {
		data(){
			return {
				markFlag: false,
				asideMenuFlag: false
			}
		},
		methods: {
			showMenu(){
				this.markFlag = true;
				this.asideMenuFlag = true;
			},
			hideMenu(){
				this.asideMenuFlag = false;
				this.markFlag = false;
			}
		}
	}
</script>

<style scoped>
	.header {
		width: 100%;
		height: 750px;
	}
	.header img {
		width: 100%;
		height: 100%;
	}
	.asideMenu {
		width: 30%;
		height: 100%;
		overflow: hidden;
		transition: width .5s;
		-moz-transition: width .5s;	/* Firefox 4 */
		-webkit-transition: width .5s;	/* Safari 和 Chrome */
		-o-transition: width .5s;	/* Opera */
		position: fixed;
		top: 0;
		right: 0;
		z-index: 10;
	}
	#home .hideMenu {
		width: 0;
	}
	#home .hideMenu .el-icon-close {
		opacity: 0;
		transform: scale(0.25) rotate(45deg);
	}
	.asideMenu .left {
		width: 18%;
		height: 100%;
	}
	.asideMenu .left i {
		margin-top: 20px;
		cursor: pointer;
		font-size: 50px;
		color: #fff;
		transition: opacity .5s ease,transform .5s ease;
		transform: scale(1) rotate(0deg);
	}
	.asideMenu .left i:hover {
		color: #409eff;
	}
	.asideMenu .right {
		width: 82%;
		height: 100%;
		background-color: rgba(88,88,88,.9);
	}
	.asideMenu .right .title {
		font-family: "Helvetica";
		letter-spacing: 10px;
		margin: 50px 30px;
		font-size: 25px;
		font-weight: 700;
		color: #fff;
	}
	.asideMenu .right .info {
		margin: 0 30px 30px;
	}
	.asideMenu .right .info li {
		padding: 20px 0;
		border-bottom: 1px solid #999;
		cursor: pointer;
		font-size: 20px;
		white-space: nowrap;
		color: #fff;
	}
	.asideMenu .right .info li:hover {
		color: #409eff;
	}
	.footer {
		height: 300px;
		overflow: hidden;
		background-color: #f0f0f0;
	}
	.footer .title {
		margin: 50px 0;
		font-size: 25px;
		font-weight: 700;
	}
	.footer .iconfont {
		font-size: 25px;
		margin: 10px;
		padding: 5px;
		cursor: pointer;
		color: #858585;
	}
	.footer .iconfont:hover {
		color: #333;
	}


	.mark {
		background-color: rgba(255,255,255,.1);
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
	}
</style>