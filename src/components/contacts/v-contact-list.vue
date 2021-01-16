<template>
  <div class="v-contact-list">
      <VContactUser
      v-for="contact in contacts"
      :key="contact.id"
      :contact_data="contact"
      @to-contact-info="toContactInfo(contact)"
      ></VContactUser>
  </div>
</template>

<script>

import VContactUser from './v-contact-user'
import {mapActions, mapState} from 'vuex'
export default {
    name: 'v-contact-list',
    components: { VContactUser },
    props: {},
    data() {
        return {
            
        }
    },
    computed:{
        ...mapState([
            'contacts'
        ])
    },
    methods: {
        ...mapActions([
            "FETCH_CONTACTS",
            "SET_USER_TO_HEADER"
        ]),
        toContactInfo(contact){
            this.$router.push({
                name: 'contact',
                query: {'id': contact.id}
            })
            this.SET_USER_TO_HEADER(contact.name)
        },

    },
    mounted(){
        this.FETCH_CONTACTS();
    }
}
</script>

<style>

</style>