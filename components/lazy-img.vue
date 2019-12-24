<template>
    <view>
        <image ref="vref" :data-src="item.src"></image>
    </view>
</template>
<script>
export default {
    props:{
        item:Object
    },
    mounted(){
        let child = this.$refs.vref;
        let observer = new IntersectionObserver(entries => {
            entries.forEach(item => {
                if(item.isIntersecting){
                    let imgUrl = item.target.dataset.src
                    item.target.childNodes[0].style.backgroundImage =  `url('${imgUrl}')`
                    item.target.childNodes[1].src = imgUrl
                }
            })
        })
        observer.observe(child._vnode.elm)
    }
}
</script>