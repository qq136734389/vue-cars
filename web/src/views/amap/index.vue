<template>
    <div class="amap-wrp">
        <el-amap vid="amapContainer"   :events="events" class="amap-demo"></el-amap>
    </div>
</template>
<script>
import { AMapManager  } from 'vue-amap';  
import { lazyAMapApiLoaderInstance } from 'vue-amap';
export default {
    name: "Index",
    data(){
        return{
            map: null,
            zoom: 16,
            events: { }

        }
    },
    mounted(){
        lazyAMapApiLoaderInstance.load().then(() => {
            this.map = new AMap.Map('amapContainer', {
                center: [121.59996, 31.197646],
                zoom: this.zoom,
            })
        })
    }
}
</script>

<style lang="scss">
    .amap-wrp{  height: 100vh;   }
</style>
