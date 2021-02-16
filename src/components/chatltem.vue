<template>
	<div class="chatitem">
		<img :style="imgStyle" :src="list.user.headerimg" alt="" />
		<div>
			<slot></slot>
		</div>
	</div>
</template>

<script>
	export default{
	props:['list'],
	data(){
		return{
			imgStyle:{
				width:"50px",
				height:"50px"
			}
		}
	}
	}
</script>

<style scoped>
	.chatitem{
		display: flex;
	}
</style>
