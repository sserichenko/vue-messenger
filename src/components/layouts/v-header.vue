<template>
  <div class="v-header">
<div class="v-header__back" 
v-if="!isCoreRoute"
@click="goBack"
>
    <i class="material-icons">keyboard_arrow_left</i>
    <span>Back</span>
</div>
<div 
class="v-header__user-info"

>
    <span v-if="!isCoreRoute">{{currentUserChat}}</span>
    <span v-else>Our users</span>
</div>
<div class="rigth-side"></div>
  </div>
</template>

<script>
import {mapState} from 'vuex'
export default {
    name: 'v-header',
    props: {},
    data() {
        return {

        }
    },
    computed: {
      ...mapState([
        "currentUserChat"
      ]),
      isCoreRoute(){
        return this.$route.path === '/'
      }
    },
    methods: {
      goBack(){
        this.$router.go(-1)
      },
      
    }

}
</script>

<style>

</style>