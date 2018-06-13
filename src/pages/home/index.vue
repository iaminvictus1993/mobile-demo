<template>
    <div>
        <Vheader :isShowCancel.sync="isShowCancel"></Vheader>
        <Slider v-show="!isShowCancel"></Slider>
        <SearchPage v-show="isShowCancel"></SearchPage>
        <Tab v-show="!isShowCancel"></Tab>
        <Hot v-show="!isShowCancel"></Hot>
    </div>
</template>

<script>
import Vheader from './header'
import SearchPage from './searchPage'
import Tab from './tab'
import Hot from './hot'
import Slider from '@/components/slider'
export default {
    data() {
        return {
            isShowCancel: false
        }
    },
    created() {},
    components: {Vheader, Slider, SearchPage, Tab, Hot},
    computed: {},
    methods: {}
}
</script>
<style lang='less' scoped>

</style>
