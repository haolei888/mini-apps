<template>
	
	<div class="list">
		<mt-header :title="home_title">
		  <router-link to="/" slot="left">
		    <mt-button icon="back">返回</mt-button>
		  </router-link>
		  <mt-button icon="more" slot="right" ></mt-button>
		</mt-header>
		
		<ul>
			<li v-for='(item,index) in arr'>
				

				<router-link :to="{ 
					path: '/article', 
					params: { userId: 123 },
					query:{
						names:str,
						idx:index
					}
				}">
					{{item.title}}

				</router-link>
		
			</li>
		</ul>
		
	</div>

</template>
<script>
	import { Header } from 'mint-ui'
	import '../../mock/mock'

export default{
	data(){
		return {
			arr:[],
			str:"",
			title:'',
			home_title:''
		}
	},
	
	mounted(){
		let id = this.$route.params.id;
		this.str = id;
		
		if (id==='yunqian') {
			this.title='yunqian'
			this.home_title='home_title'
		} 
		
		this.$http({
			method:"get",
			url:'/arList'
		})
			.then(res=>{
				this.arr = res.data[id]['fenlei'];
				this. home_title= res.data[id]['home_title'];
			})
	}

}
</script>

<style scoped="">
	.mint-header{
		background:#fd70a4;
	}
	.list{
		width: 100%;
		height: 100%;
		position: absolute;
		left: 0px;
		top: 0px;
	}
	ul li{
		font-size:14px;
		padding:10px;
		border-bottom: 1px solid #FE7B7C;
		text-align: start;
		list-style: none;
	}
	ul li a{
		text-decoration: none;
		color: #220e0a;
	}	
</style>