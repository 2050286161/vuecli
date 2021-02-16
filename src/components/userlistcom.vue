<template>
	<div class="userlist">
		<h1>用户列表</h1>
		<ul>
			<li v-for="(item,index) in userlist" :key="index" @click="chooseUser(index)">
				<img :src="item.headerimg"/>
				<h3>{{item.username}}</h3>
			</li>
		</ul>
	</div>
</template>

<script>
export default{
	data(){
		return{}
	},
	props:['userlist'],
	methods:{
		chooseUser:function(e){
			// 将选择用户的事件触发发送给到父元素
			this.$emit('chooseuser',e)
		}
	}
}
</script>

<style scoped>
	.userlist{
		width: 300px;
		height: 700px;
		background-color: skyblue;
	}
	.userlist ul li img{
		width: 80px;
		height: 80px;
	}
	.userlist ul li{
		display: flex;
	}
	.redbag{
		background-color: pink;
	}
</style>
