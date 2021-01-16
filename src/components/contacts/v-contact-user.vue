<template>
  <div class="v-contact-user" @click="toContactInfo">
    <div class="user__avatar"></div>
    <div class="user__name">
        <span>{{contact_data.name}}</span>
    </div>
    <div 
    class="user__status"
 :class="{ 'online': contact_data.status === 'online', 'offline': contact_data.status === 'offline' }"
    >

    </div>
  </div>
</template>

<script>
export default {
    name: 'v-contact-user',
    props: {
        contact_data: {
            type: Object,
            default: () => {}
        }
    },
    data() {
        return {
            
        }
    },
    computed:{},
    methods: {
        toContactInfo(data){
            this.$emit('to-contact-info', this.contact_data)
        }
    }
}
</script>

<style>

</style>