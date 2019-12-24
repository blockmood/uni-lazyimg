<template>
    <view>
        <view class="img-list" >
			<image v-for="(item,index) in group" :key="index" ref="vref" class="lazy-image" :data-src="item.src" ></image>
		</view>
    </view>
</template>
<script>
   
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
    },
    mounted(){
        var child = this.$refs.vref;
        let observer = new IntersectionObserver(entries => {
            entries.forEach(item => {
                if(item.isIntersecting){
                    let imgUrl = item.target.dataset.src
                    item.target.childNodes[0].style.backgroundImage =  'url('+imgUrl+')' 
                    item.target.childNodes[1].src = imgUrl
                }
            })
        })
        child.forEach(item => observer.observe(item._vnode.elm))

    },
    destroyed () {
        
    }
}
</script>
<style lang="scss" scoped>
    .lazy-image{
        margin-bottom: 500px;
    }
</style>