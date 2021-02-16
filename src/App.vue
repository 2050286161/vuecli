<template>
	<div id="App">
		<!-- <h1>{{msg}}</h1> -->
		<div class="content">
			<chatcom :currentuser="currentUser"></chatcom>
			<userlist :userlist="userlist_" @chooseuser="toggleUser"></userlist>
		</div>
  </div>
</template>

<script>
import chatcom from './components/chatcom.vue'
import userlist from './components/userlistcom.vue'
export default {
  name: 'App',
  components: {
    chatcom,userlist
  },
  data(){
	  return{
		msg:'老陈聊天',
		userlist_:[
			{
				username:"小明",
				headerimg:require("./assets/img/1.jpg")
			},
			{
				username:"小黑",
				headerimg:require("./assets/img/2.jpg")
			},
			{
				username:"小红",
				headerimg:require("./assets/img/3.jpg")
			},
			{
				username:"小白",
				headerimg:require("./assets/img/4.jpg")
			}
		],
		currentUser:{
			username:"小明",
			headerimg:require("./assets/img/1.jpg")
		}
		
	  }
	  },
	  methods:{
		  toggleUser:function(e){
			  this.currentUser=this.userlist_[e]
		  }
	  }
}
</script>

<style scoped>
.content{
	display: flex;
	width: 50rem;
	height: 43.75rem;
	margin: 0 auto;
}
</style>
