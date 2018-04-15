<template>
    <div class="fav">
    	<mt-header fixed title="收藏"></mt-header>
      	
      	<div class="fav-main">
      		
      		<ul> 			
      			<li v-for="item in arr">
	      			<mt-cell-swipe
					  :title="item"
					  :right="[
					    {
					      content: 'Delete',
					      style: { background: 'pink', color: '#fff' },
					      handler: () => this.$messagebox('delete')
					    }
					  ]">
					</mt-cell-swipe>
      				
      			</li>
      		</ul>
      		
      	</div>
      	
    
    </div>
</template>
<script type="text/javascript">
	import { Header,CellSwipe  } from 'mint-ui'
	export default{
		data(){
			return {
				arr:[],
				val:'',
				item:''
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
	.fav{
		width: 100%;
		height: 100%;
		position: absolute;
		left: 0px;
		top: 0px;
	}
	.fav-main{
		margin-top: 40px;
	}
	.fav-main ul li{
		list-style: none;
		font-size: 16px;
		color: #454545;
		margin-left: 20px;
	}
	
</style>


