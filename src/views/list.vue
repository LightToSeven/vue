<template lang="html">
    <div class="list">
        <list-items v-for='item in listItems' :key="item.id" :phone='item'>

        </list-items>
    </div>
</template>
<script >
    import listItems from './items.vue'
    export default{
        data(){
            return{
                listItems:[
                    {
                        id:0,
                        name:'vasya',
                        tel:'099999999'
                    },
                    {
                        id:1,
                        name:'vasya2',
                        tel:'099999999'
                    }
                ]
            }
        },

        components:{
            listItems
        }
    }
</script>
<style lang="scss">

</style>