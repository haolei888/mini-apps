<template>
    <div class="history">
    	<mt-header fixed title="历史记录"></mt-header>
      	
      	<div class="history-main">
      		<ul>
      			<li v-for="item in arr">
      				{{item}}
      				
      			</li>
      		</ul>
      		
      		
      	</div>
      	
    
    </div>
</template>
<script type="text/javascript">
	import { Header} from 'mint-ui'
	export default{
		data(){
			return {
				arr:[],
				val:''
			}
		},
		mounted(){
			let local=localStorage;
			let meStr = local.getItem("f");
			let arr = JSON.parse(meStr);
			let str = "";
			arr.forEach(item=>{
				str+="a"+item;
			})
			let brr=str.split('a')
			this.arr=brr;
			
			this.$http({
				method:"get",
				url:'/arList'
			}).then(res=>{
				console.log(this.$route)
			})
			
			
			
			
		}
	}
	
</script>
<style type="text/css" scoped="">
	.mint-header{
		background:#fd70a4;
	}
	.history{
		width: 100%;
		height: 100%;
		position: absolute;
		left: 0px;
		top: 0px;
	}
	.history-main{
		margin-top:40px;
	}
	.history-main ul li{
		list-style: none;
		padding-left:10px;
		font-size: 16px;
		color: #454545;
		line-height:34px;
	}
</style>