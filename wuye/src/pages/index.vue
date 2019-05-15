<style scoped>
.wuye{font-family: PingFangSC-Regular;width: 100%;height:100%;
      background-color:#e5e2dd;font-size: 14px;text-align: center}
a{color: #000;opacity: 0.7;}	
.address{padding: 14px;background-color: #f7f7f9;font-family: "微软雅黑";
    font-size: 14px;color: #000000;text-align: center;}
.swiper{width: 100%;}
.swiper img{width: 100%;}
.city{float: left;}
.xiaoqu{padding-right: 32px;font-size:16px;font-weight: bold;}
.section2{width: 100%;background-color: #f7f6f1;height: 53px;
    overflow:hidden;vertical-align: middle;}
.section2_sub_img{width: 28px;height: 23px;margin: 15px 4% 15px 4%;float: left;}
.section2_sub_txt1{float: left;margin: 18px 4% 12px 0px;
    font-size: 15px;color: #ff0000;}
.section2_sub_txt2{margin: 20px 0px 12px 0px;float: left;font-size: 14px;}
.section2_sub_txt2 a{text-decoration: none;color: #a6937c;font-size: 14px;}
.section_divider{border-bottom: 10px solid #e5e2dd;}
.jiugongge{width: 100%;height: 208px;background-color: white;}
.jgg_li{float: left;width:calc((100% / 3) - 4px);height: 104px; text-align: center;letter-spacing: 1.31px;font-size: 16px;font-family:PingFangSC-Regular;
	border: 1px solid #efefef}
.jgg_li:nth-child(1){border-left:none;}
.jgg_li:nth-child(3){border-right: none;}
.jgg_li:nth-child(4){border-left: none;}
.jgg_li:nth-child(6){border-right: none;}
.jgg_img{margin: 15px auto 3px;}
.jgg_img img{width: 54px;}
.jgg-span{color: black;}

.inner{width: 100%;height: 350px;overflow: hidden; background-color: white;}
.inner1{width: 80%;height: 20px; margin:15px auto 15px;line-height: 20px;}
.spanl{font-size: 18px;letter-spacing: 1.38px;}
.spanr{font-size: 12px;letter-spacing: 1.12px;opacity: 0.5;color: #171717;padding-top: 3px;}
.title_li{width: 86%;height: 100px;overflow: hidden;margin: 0 auto;position: relative;}
/* .title_li div{float: left;} */
.title_img{width: 30%;height:86px;position: absolute;margin-left: 0;margin-top: 7px}
.title_img img{width: 100%;height:100%;margin:auto;}
.title_news{font-size: 14px; width: 70%;height: 85px; text-align: left;position: absolute;margin-left: 30%;margin-top:7px;}
.title_news span{padding: 0 20px;color: black;}
.xiaxian{height:1px;width:100%;background-color:#ccc; margin-top: 7px;}
p{padding: 0 20px;color: #565252;letter-spacing: 1.14px;overflow: hidden;
    display: -webkit-box;-webkit-line-clamp: 2;-webkit-box-orient: vertical;
    overflow: hidden;height: 34px;line-height: 17px;}
h6{text-align: right; padding: 0 15px;font-size: 11px;color:rgba(0,0,0,0.63);letter-spacing: 0.9px;}
</style>
<template>
	<div  class="wuye">
		  <swiper :options="swiperOption">
          <swiper-slide v-for="(item,index) in banners" :key="index">
          <!-- <router-link :to="{path:'/classify',query:{id:14}}"> -->
            <div class="swiper">
              <a :href="item.bannerUrl">
                <img :src="item.picture" alt="">     
              </a>      
            </div> 
          <!-- </router-link> -->
          </swiper-slide>
          <div class="swiper-pagination" slot="pagination"></div>    
      </swiper>
	    <div class="jiugongge">
            <ul>
                <li class="jgg_li" >
                    <router-link :to="{path:'/pay',query:{id:'a'}}">
                        <div class="jgg_img">
                            <img src="../assets/images/icon_shequ_wuyejiaofei_03.png" alt="">
                        </div>
                        <span class="jgg-span">物业缴费</span>
                    </router-link>
                </li>
                <li class="jgg_li" >
                    <router-link to="/payEnquiry">
                        <div class="jgg_img">
                            <img src="../assets/images/icon_shequ_jiaofeichaxun_03.png" alt="">
                        </div>
                        <span class="jgg-span">缴费查询</span>
                    </router-link>
                </li>
                <li class="jgg_li" >
                    <div @click="alert">
                        <div class="jgg_img">
                            <img src="../assets/images/icon_sheuq_shequfuwu_03.png" alt="">
                        </div>
                        <span class="jgg-span">社区服务</span>
                    </div>
                </li>
                <li class="jgg_li" >
                    <router-link to="/myHouse">
                        <div class="jgg_img">
                            <img src="../assets/images/icon_shequ_woshiyezhu_03.png" alt="">
                        </div>
                        <span class="jgg-span">我是业主</span>
                    </router-link>
                </li>
                <li class="jgg_li" >
                    <router-link :to="{path:'/reply',query:{category:'9'}}">
                        <div class="jgg_img">
                            <img src="../assets/images/icon_shequ_linglijiwai_03.png" alt="">
                        </div>
                        <span class="jgg-span">邻里叽歪</span>
                    </router-link>
                </li>
                <li class="jgg_li" >
                    <router-link :to="{path:'/reply',query:{category:'4'}}">
                        <div class="jgg_img">
                            <img src="../assets/images/icon_shequ_ershoushichang_03.png" alt="">
                        </div>
                        <span class="jgg-span">二手市场</span>
                    </router-link> 
                </li>
            </ul>
        </div>
        <div class="section2">
            <div class="section2_sub">
                <img class="section2_sub_img" src="../assets/images/shequgonggao_03.png"/>
                <div class="section2_sub_txt1">公告</div>
                <div class="section2_sub_txt2" >
                    <div style="vertical-align: middle;"><a href="http://mp.weixin.qq.com/s?__biz=MzIyMjI2NDkzMg==&mid=100000013&idx=1&sn=6944e371c60d785a9e9e07dd4e84d148&scene=0&previewkey=y0B5npPwOWIki38sKTwIXO7Ymkb%2FrTtdeduSyhARBMI%3D#wechat_redirect" style="height: 150px;">祝贺“春晖”微信公众号上线！</a></div>
                </div>
            </div>
        </div>
        <div class="section_divider"></div> 
        <div class="inner">
          <div class="inner1">
            <span class="spanl fl"><strong>社区资讯</strong></span>
            <span class="spanr fr">更多&gt;</span>
          </div>
          <ul class="title_ul"> 
            <li class="title_li" v-for="(news,index) in messageData" :key="index">
              <div v-on:click="href(news.id)">
                <div class="title_img"> 
                  <img v-bind:src="news.smallImage" alt="">
                </div>
                <div class="title_news">
                  <p>{{news.summary}}</p>
                  <!-- <span>…</span> -->
                  <br>
                  
                  <h6 style="margin-top:10px;">生活百科</h6>
                </div>
                <div class="xiaxian"></div>
              </div>                        
            </li>
          </ul>
        </div>
		<div style="width: 100%;height: 90px;background: white"></div>
		<foot></foot>
	</div>
</template>
<script>
    let vm;
    import { MessageBox } from 'mint-ui';
	import foot from '../components/footer.vue'
  import {swiper,swiperSlide} from 'vue-awesome-swiper'
  import '../assets/css/swiper.min.css'
	export default {
		components:{
			foot,
      swiper,
        swiperSlide
		},
		data(){
			return {
        swiperOption:{
            notNextTick:true,
            autoplay:true,
            autoplay:{
              disableOnInteraction:false,
              delay:2000
            },
            speed:1000,
            pagination: {
              el: '.swiper-pagination',
              clickable:true,
            },
            loop: true,             
        },
        banners:[],
        bannerType:3,
				selected: '1',
				items1:'',
				messageData:''
			}
		},
		beforeCreate(){//刷新页面
			
		},
		created(){
            vm = this;
		},
		watch:{
			
		},
		mounted(){
			// this.initSession4Test();
            this.initUserInfo();
		},
		methods:{
			//模仿线上用户信息
			//105/747/384
		  	initSession4Test(){
		  		let _this = this;
				let url = '/initSession4Test/105';
				_this.receiveData.getData(_this,url,'Data',function(){
					_this.message();
          vm.banner()
				});
			},
            initUserInfo(){
                let n = "GET",
                    a = "userInfo",
                    i = null,
                    e = function(n) {
                        // console.log(JSON.stringify(n));
                        vm.message();
                        vm.banner()
                    },
                    r = function() { 

                    };
                this.common.invokeApi(n, a, i, null, e, r);
            },
            alert() {
                MessageBox('该功能暂未开放','尽请期待!');
            },
			message(){
				// let _this = this;
				let page = 0;
				let url = 'messages/'+page;
				vm.receiveData.getData(vm,url,'res',function(){
					console.log(vm.res);
					vm.messageData = vm.res.result;
				})
			},
      banner(){
        let url = "banner/"+vm.bannerType;
        vm.receiveData.getData(vm,url,'res',function(){
          console.log(vm.res);
          vm.banners = vm.res.result;
        })
      },
			href(mid){
                if(mid==1){
                   window.location.href="http://mp.weixin.qq.com/s?__biz=MzIyMjI2NDkzMg==&mid=100000001&idx=6&sn=f1d2aa14684b2041095ddcc3c757927a&scene=0&previewkey=koIZjFK%2FvSTLuEWTZbl26MwqSljwj2bfCUaCyDofEow%3D#wechat_redirect";
               }else if(mid==2){
                   window.location.href="http://mp.weixin.qq.com/s?__biz=MzIyMjI2NDkzMg==&mid=100000001&idx=5&sn=7c78875d3f80c92ec490bfb22362bc58&scene=0&previewkey=koIZjFK%2FvSTLuEWTZbl26MwqSljwj2bfCUaCyDofEow%3D#wechat_redirect";
               }else if(mid==3){
                   window.location.href="http://mp.weixin.qq.com/s?__biz=MzIyMjI2NDkzMg==&mid=100000001&idx=4&sn=d1e05a8d8d63e34986324e82d3c7d483&scene=0&previewkey=koIZjFK%2FvSTLuEWTZbl26MwqSljwj2bfCUaCyDofEow%3D#wechat_redirect";
               }else if(mid==4){
                   window.location.href="http://mp.weixin.qq.com/s?__biz=MzIyMjI2NDkzMg==&mid=100000001&idx=3&sn=24587567042210be740335615493225e&scene=0&previewkey=koIZjFK%2FvSTLuEWTZbl26MwqSljwj2bfCUaCyDofEow%3D#wechat_redirect";
               }else if(mid==5){
                   window.location.href="http://mp.weixin.qq.com/s?__biz=MzIyMjI2NDkzMg==&mid=100000001&idx=2&sn=8948b2a3c709b3dc8da5b2d3117716aa&scene=0&previewkey=koIZjFK%2FvSTLuEWTZbl26MwqSljwj2bfCUaCyDofEow%3D#wechat_redirect";
               }else if(mid==6){
                   window.location.href="http://mp.weixin.qq.com/s?__biz=MzIyMjI2NDkzMg==&mid=100000001&idx=1&sn=ef563f8358b55f4a379f81833d323fbb&scene=0&previewkey=koIZjFK%2FvSTLuEWTZbl26MwqSljwj2bfCUaCyDofEow%3D#wechat_redirect";
               }else{
                   this.$router.push({
                        path:'/news',
                        query:{
                            messageId:mid
                        }
                    })
               }
	          
	        },

		}
	}
</script>