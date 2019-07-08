<template>
    <div class="wrapper">
        <swiper :options="swiperOption" v-if="showSwiper">
            <!-- slides -->
            <swiper-slide v-for="item of list" :key="item.id">
                <img class="swiper-img" :src="item.imgUrl">
            </swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination"  slot="pagination"></div>
            <!-- <div class="swiper-button-prev" slot="button-prev"></div>
            <div class="swiper-button-next" slot="button-next"></div>
            <div class="swiper-scrollbar"   slot="scrollbar"></div> -->
        </swiper>
    </div>
</template>

<script>
export default {
    name:'HomeSwiper',
    props: {
        list: Array
    },
    data (){
        return{
            swiperOption: {
                pagination:'.swiper-pagination',
                loop:true,
                autoplay:3000,
                autoplayDisableOnInteraction:false
            },
            // swiperList: [{
            //     id:"swiper-1",
            //     imgUrl:"http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/d7bbc21db442366a882e04ddc984669a.jpg_750x200_85e640d9.jpg"
            // },{
            //     id:"swiper-2",
            //     imgUrl:"http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20196/7338e652340b8b9135111e6157fd5650.jpg_750x200_f4973a1e.jpg"
            // },{
            //     id:"swiper-3",
            //     imgUrl:"http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20195/5eb82a8ca5b0cebb2c3ae1a53a4d8f81.jpg_750x200_645bfba1.jpg"
            // },{
            //     id:"swiper-4",
            //     imgUrl:"http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20196/b67d0455e3514059d6589496cc81b007.jpg_750x200_f9aab4c7.jpg"
            // }]
        }
    },
    computed: {
        showSwiper () {
            return this.list.length
        }
    },
}
</script>

<style lang="stylus" scoped>
    .wrapper>>>.swiper-pagination-bullet-active
        background-color #fff
    .wrapper
        overflow hidden
        width: 100%
        height:0
        padding-bottom:26.6% 
        background: #eee
        .swiper-img
            width: 100%
</style>
