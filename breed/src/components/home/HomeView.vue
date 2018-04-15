
<template>
    <div class="home">
      	<mt-header fixed title="孕育宝典"></mt-header>
    	<div class="container">
    		<ul>
    			<li>
    				<router-link to="/list/yunqian">
    					<img src="../../assets/img/pic1.png"/>
    				</router-link>
    			</li>
    			<li>
    				<router-link to="/list/yunzhong">
    					<img src="../../assets/img/pic2.png"/>
    				</router-link>
    			</li>
    			<li>
    				<router-link to="/list/chanqian">
    					<img src="../../assets/img/pic3.png"/>
    				</router-link>
    			</li>
    			<li>
    				<router-link to="/list/chanhou">
    					<img src="../../assets/img/pic4.png"/>
    				</router-link>
    			</li>
    			<li>
    				<router-link to="/list/chengzhang">
    					<img src="../../assets/img/pic5.png"/>
    				</router-link>
    			</li>
    			<li>
    				<router-link to="/list/fangzhi">
    					<img src="../../assets/img/pic6.png"/>
    				</router-link>
    			</li>
    		</ul>
    	</div>
    	
    	
    </div>
</template>
<script type="text/javascript">
	import { Header } from 'mint-ui'
	export default{
		
	}
</script>
<style type="text/css" scoped="">
.home{
	width: 100%;
	height: 100%;
	position: absolute;
	left: 0px;
	top: 0px;
}
	.container{
		border: 1px solid #ccc;
		margin-top: 40px;
	}
	.container ul li{
		list-style: none;
		margin-bottom: 25px;
	}
	.container ul li img{
		width: 90%;
		margin-left: auto;
		margin-right: auto;
		display: block;
	}
	.mint-header{
		background:#fd70a4;
	}
</style>