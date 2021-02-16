<template>
	<div class="chat">
		<h1 class="user">用户:{{currentuser.username}}</h1>
	<!-- 聊天列表 -->
	<div class="chatlist">
		<chatitem v-for="item,index in chatList" :list="item" :key="index">
			{{item.chatcontent}}
		</chatitem>
	</div>
	<chatinput :sendEvent="sendEvent"></chatinput>
	</div>
</template>

<script>
import chatinput from './chatinputcom.vue'
import chatitem from './chatltem.vue'
	export default{
		props:['currentuser'],
		components:{
			chatinput,chatitem
		},
		data(){
			return{
			chatList:[
				{
					user:{
						username:"小明",
						headerimg:require("../assets/img/1.jpg")
					},
					chatcontent:"吃了吗"
				}
			]
		}
		},
		methods:{
			sendEvent:function(e){
				this.chatList.push({
					user:{
						username:this.$root.currentUser,
						headerimg:require("../assets/img/1.jpg")
					},
					chatcontent:e
				})
				this.chatList.push({
					user:this.$root.currentUser,
					chatcontent:new Date()
				})
			}
		}
	}
</script>

<style scoped>
	.chat{
		width: 500px;
		height: 700px;
		border: 1px solid #ccc;
	}
</style>
