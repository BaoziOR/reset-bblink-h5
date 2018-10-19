<template>
	<div>
		<header class="headerBar_content">
			<p @click="handleCick"></p>
			<h1>{{title}}</h1>
			<span></span>
		</header>
	</div>
</template>
<script>
	export default {
		data() {
			return {
			}
		},
		props:{
			title:{
				type:String,
				default:'bblink'
			},
			handleCick:{
				type:Function,
				default:() => {
					window.history.go(-1)	
				}
			}
		}
	}
</script>
<style lang="scss">
 	@import'@/assets/sass/common/_function.scss';
	.headerBar_content {
		display: flex;
		justify-content: space-between;
		align-items: center;
		background: #fff;
		padding: 0 ptr(15);
		p{
			font-size: ptr(16);
			width: ptr(75);
			line-height: ptr(44);
			position: relative;
			height: ptr(44);
			&::before{ 
				content:'';
				display: block;
				position: absolute;
				left: 0;
				top: 50%;
				transform:translateY(-50%) Rotate(45deg);
				width: ptr(10);
				height: ptr(10);
				border: 1px solid #ccc;
				border-right: 0;
				border-top: 0;

			}

		}
		h1{
			font-size: ptr(16);
			line-height: ptr(44);
			flex:1;
			text-align: center;
			overflow: hidden;
			text-overflow:ellipsis;
			white-space: nowrap;
		}
		span{
			display: block;
			width: ptr(75);
			line-height: ptr(44);
			text-align: center;
			height: ptr(44);
		}
	}
</style>