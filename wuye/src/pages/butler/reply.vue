<style scoped>
    .box{font-family: PingFangSC-Regular;width: 100%;height:100%;font-size: 14px;}
    .nav{width: 100%;height: 87px;border-bottom: 1px solid #ccc;background: #f7f7f1}
    .tab{height: 100%;width:calc((100% / 3) - 2px);float: left;text-align: center;}
    .tab:nth-child(2){border-left: 1px solid #ccc;border-right: 1px solid #ccc;}
    .tab_active{background: #fff;color: #ff8a00;}
    .tab_div{width: 40px;height: 40px;margin:12px auto 10px;}
    .tab_div img{width: 100%;height: 100%;margin: auto;}

    .submit-btn-black {height: 35px;margin-left: 1%;line-height: 35px;
        background: #3b3738;text-align: center;}
    .submit-btn-orange2 {height: 35px;margin-right: 0;line-height: 35px;
        background: #ff8a00;text-align: center;}
    .preview_img_layer{float: left;width: 100%;}
    .sub_img_layer{float:left;padding-bottom:15px;width: 32%;
        margin-right: 1%;}
    .preview_img{width: 100%;height: 94px;}
    
    .thread-picture { width: 42px;height: 42px;margin-right: 15px;
        border: 1px solid #d4cfc8;border-radius: 42px;}
    .thread_user_name{font-size: 14px;margin-top: 10.5px;color: #3b3937;
        height: 21px;line-height: 21x;width: 45%;float: left;}  
    .thread_user_addr{margin: 10.5px 0px 0px 0px;color: #666; float: left;
        font-size: 12px;height: 21px;line-height: 21x;
        text-align: right;width: 33%;}
    
</style>
<template>
    <div class="box">
        <div v-show="tab1Data.length!==0">
            <div class="thread-item p15 lite-divider" style="border-bottom: 2px solid #d4cfc8;"v-for="(item,index) in tab1Data" 
                :key="index" v-show="tab1Data.length!=0">
                <div class="ov" style="width: 100%;">
                    <div>
                        <img class="fl thread-picture" :src="item.userHead" />
                    </div>
                    <div class="thread_user_name">{{item.userName}}</div>
                    <div class="thread_user_addr">{{item.userSectName}}</div>
                </div>
                <div class="ov pt15 pb15 fs13" style="color: #3b3937">{{item.threadContent}}</div>
                <div class="preview_img_layer" >
                    <div v-for="(img,index) in item.previewLink">
                        <div class="sub_img_layer" >
                            <img class="preview_img" :src="img" />
                        </div>
                    </div>
                </div>
                <div class="fs13" style="color: #a6937c; line-height: 23px; width: 100%;">
                    <img style="width: 13px; height: 13px;" src="../../assets/images/icon_time_gray.png"/>&nbsp;{{item.formattedDateTime}}
                    <div class="fr pr15 comment" style="text-align: right;" @click="goReply(item.threadId)" ><img style="width: 13px; height: 13px;" src="../../assets/images/icon_comment_gray.png"/>&nbsp;{{item.commentsCount}}</div>
                </div>
            </div>
        </div>
        <div v-show="tab1Data.length==0" style="width: 100%;height: 100%;">
            <img style="width: 100%;" src="../../assets/images/bg_publish.jpg" alt="">
        </div>
        
        <div style="width: 100%;height: 80px;"></div>
        <div style="position: fixed; bottom:0.5px;width: 100%;color: white;">
            <div class="submit-btn-black fs14 fl" style="width: 25%" @click="back()">返回</div>
            <div class="submit-btn-orange2 fs14 fl" style="width: 73%" @click="public">我要发布</div>
        </div>
    </div>
</template>
<script>
    let vm;
    export default {
        data(){
            return {
                userId:'',
                category:this.$route.query.category,
                tab1: true,
                tab1Data: '',
                tab1_active:false,
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
            this.initData1()
            
        },
        methods:{
            initData1(){
                let url = '/thread/getThreadList/n/0';
                let obj = {
                    filter: 'n',
                    threadCategory: this.$route.query.category
                };
                vm.receiveData.postData(vm,url,obj,'res',function () {
                    // body...
                    console.log(vm.res);
                    if(vm.res.success == true){
                        vm.tab1Data = vm.res.result;
                    }
                    
                })
            },
            goReply(id){
                console.log(id);
                this.$router.push({
                    name:'indexReply',
                    query:{
                        Id:id,
                        category:this.$route.query.category
                    }
                })
            },
            back(){
                this.$router.push({path:'/'})
            },
            public(){
                this.$router.push({
                    path:'/suggest',
                    query:{
                        category:vm.category
                    }
                }) 
            }
        }
    }
</script>