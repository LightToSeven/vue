<template lang="html">
    <div class="list">
        <input type="text" v-model="name" placeholder="name">
        <input type="text" v-model="phone" placeholder="phone">
        <input type="text" v-model="search">
        <button type="button" @click="addContacts()" name="button">Клик</button>
        <list-items v-for='item in filteredList' :key="item.id" :phone='item'>
        </list-items>
    </div>
</template>
<script >
    import listItems from './items.vue'
    export default{
        data(){
            return{
                name:'',
                phone:'',
                search:'',
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
        methods:{
            addContacts(){
                const obj={
                    id: this.listItems.length + 1,
                    name: this.name,
                    tel: this.phone
                }
                this.listItems.push(obj);
                this.clearInput();
            },
            clearInput(){
                this.name='',
                this.phone=''
            }
        },
        computed:{
            filteredList: function(){
                var comp = this.search;
                return this.listItems.filter(function (elem) {
                    if(comp==='') return true;
                    else return elem.name.indexOf(comp) > -1;
                })
            }
        },
        components:{
            listItems
        }
    }
</script>
<style lang="css">

</style>