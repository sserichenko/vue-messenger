<template>
  <div class="v-main-wrapper">
<v-header/>
<router-view/>
<v-bottom-nav/>
  </div>
</template>

<script>
import VBottomNav from './layouts/v-bottom-nav.vue'
import vHeader from './layouts/v-header.vue'
export default {
     name: 'v-main-wrapper',
  components: { vHeader, VBottomNav },
    props:{},
    data(){
        return {

        }
    },
    computed: {

    }
}
</script>

<style>

</style>