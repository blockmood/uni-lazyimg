<template>
    <view>
        <view class="img-list" >
            <view class="item_c" v-for="(item,index) in group" :key="index">
                <lazyImg :item="item"/>
            </view>
        </view>
    </view>
</template>
<script>
   
   import lazyImg from '../../components/lazy-img'

    export default {
        data (){
            return {
                group: [
                    {
                        src: "//img-cdn-qiniu.dcloud.net.cn/static/images/side/uniapp-mall.png",
                    },
                    {
                        src:"https://oimageb6.ydstatic.com/image?id=-618308228018432514&product=adpublish&w=520&h=347"
                    },
                    {
                        src:'https://camo.githubusercontent.com/c156285977609c7bb08a2f9ff8970445d8fd6be7/687474703a2f2f696d672d63646e2d71696e69752e64636c6f75642e6e65742e636e2f756e696170702f74656d706c6174652f6e65772e706e67'
                    },
                    {
                        src:"https://cn.vuejs.org/images/logo.png"
                    },
                    {
                        src: "//img-cdn-qiniu.dcloud.net.cn/static/images/side/uniapp-mall.png",
                    },
                    {
                        src:"https://oimageb6.ydstatic.com/image?id=-618308228018432514&product=adpublish&w=520&h=347"
                    },
                    {
                        src:'https://camo.githubusercontent.com/c156285977609c7bb08a2f9ff8970445d8fd6be7/687474703a2f2f696d672d63646e2d71696e69752e64636c6f75642e6e65742e636e2f756e696170702f74656d706c6174652f6e65772e706e67'
                    },
                    {
                        src:"https://cn.vuejs.org/images/logo.png"
                    }
                ]
        }
    },
    methods:{
        
    },
    components: {
        lazyImg
    },
}
</script>
<style lang="scss" scoped>
    .lazy-image{
        margin-bottom: 500px;
    }
    .item_c{
        margin-bottom: 500px;
    }
</style>