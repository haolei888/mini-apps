<template>
    <div class="foot">
    	<mt-tabbar v-model="selected" fixed>
			<mt-tab-item id="首页">
				<router-link to="/home">
					首页
				</router-link>
			</mt-tab-item>
			<mt-tab-item id="收藏">
				<router-link to="/fav">
					收藏
				</router-link>
			</mt-tab-item>
			<mt-tab-item id="历史记录">
				<router-link to="history">
					历史记录
				</router-link>
			</mt-tab-item>
			<mt-tab-item id="设置">
				<router-link to='config'>
					设置
				</router-link>
			</mt-tab-item>
		</mt-tabbar>
    </div>
</template>
<script type="text/javascript">
	import { Tabbar, TabItem } from 'mint-ui'
	export default{
		data(){
			return {
				selected:''
			}
		}
	}
</script>
<style type="text/css" scope>
	.foot a{
		text-decoration: none;
		color: #fc70a4;
		font-size: 14px;
	}
</style>