<template>
  <div class="v-users-list">
      <v-user 
      v-for="chat in chats"
      :key="chat.id"
        :user_data="chat"
      />
  </div>
</template>

<script>
import vUser from './v-user.vue'
import {mapActions, mapState} from 'vuex'
export default {
    name: 'v-users-list',
    components: { vUser },
    props: {},
    data() {
        return {
            
        }
    },
    methods: {
        ...mapActions([
            "FETCH_CHATS",
            "SET_USER_TO_HEADER"
        ])
    },
    computed: {
        ...mapState([
            "chats"
        ])
    },
    mounted(){
        this.FETCH_CHATS();
        this.SET_USER_TO_HEADER();
    }

}
</script>

<style>

</style>