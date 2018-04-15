<template>
    <div class="config">
    	<mt-header fixed title="设置"></mt-header>
      	
      	<div class="config-main">
      		<mt-cell title="我的关注" is-link>
			  <span style="color: green"></span>
			</mt-cell>
			<mt-cell title="最热" is-link>
			  <span style="color: green"></span>
			</mt-cell>
			<mt-cell title="八卦闲聊" is-link>
			  <span style="color: green"></span>
			</mt-cell>
			<mt-cell title="专家在线" is-link>
			  <span style="color: green"></span>
			</mt-cell>
			
			<mt-cell title="小提醒" is-link>
			  <span style="color: green"></span>
			</mt-cell>
			<mt-cell title="小工具" is-link>
			  <span style="color: green"></span>
			</mt-cell>
			<mt-cell title="设置" is-link>
			  <span style="color: green"></span>
			</mt-cell>
			
						
      	</div>
      	
    
    </div>
</template>
<script type="text/javascript">
	import { Header,Cell} from 'mint-ui'
	
	export default{
		
	}
	
</script>
<style type="text/css" scoped="">
	.mint-header{
		background:#fd70a4;
	}
	.config{
		width: 100%;
		height: 100%;
		position: absolute;
		left: 0px;
		top: 0px;
	}
	.config-main{
		margin-top: 40px;
	}
	.mint-cell-mask{
		border-bottom: 2px solid #454545;
		color: #454545;
		font-size: 14px;
	}
</style>
