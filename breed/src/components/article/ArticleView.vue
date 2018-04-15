<template>
	
	<div class='ar'>
		<mt-header :title="title">
		    <mt-button icon="back" slot="left" @click="returns">返回</mt-button>	 	
			<div class="btn" slot="right"  @click="fav">
				<img src="../../assets/img/scc.png"/>
			</div>
		</mt-header>
		
		{{content}}
		
	</div>

</template>

<script>
import { Header } from 'mint-ui'

	
export default{
	data(){
		return {
			content:"",
			title:''
		}
	},
	methods:{
		returns(){
			this.$router.history.go(-1);
		},
		fav(){
			let local=localStorage;
			let nmu='';
			if(  !local.getItem("f")  ){
				let arr=local.setItem("f","[]");
			}
			let brr = JSON.parse(local.getItem("f"));
			
			if(brr.includes(this.title)){
				alert("已经收藏过了")
			}else{
				brr.push(this.title)
				alert("恭喜！收藏成功")
			}
			brr.forEach((val,idx)=>{
				nmu+=val;
			})
			let b=JSON.stringify(brr)
			local.setItem('f',b)
			
		}
	},
	mounted(){
		let names = this.$route.query.names;
		let idx = this.$route.query.idx;

		this.$http({
			method:"get",
			url:'/arList'
		})
		.then(res=>{
			this.content = res.data[names]['fenlei'][idx].content
			this.title = res.data[names]['fenlei'][idx].title
		})
	}
}	
</script>

<style scoped="">
	.mint-header{
		background:#fd70a4;
	}
	.ar{
		width: 100%;
		height: 100%;
		position: absolute;
		left: 0px;
		top: 0px;
		font-size:16px;
		color: #454545;
	}	
</style>

