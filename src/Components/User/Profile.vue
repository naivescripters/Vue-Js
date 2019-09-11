<template>
    <div>
        <div class="user_profile">
            <h3>User Information:</h3>
            <ul>
                <li><span>Name:</span>{{userName}}</li>
                <li><span>Lastname:</span>{{userLastName}}</li>
                <li><span>Age:</span>{{userAge}}</li>
            </ul>
            <h3>Parents</h3>
            <ul>

                <li v-for="(key,value,index) in userParents" :key="index">
                    <span>{{value}}:</span>
                    {{key}}
                </li>
                
            </ul>
        </div>

        <button @click="updateName">Update Name</button>
        <button @click="updateLastName('Jami')">Update Lastname</button>
        <div>
            <input type="text" v-model="friendInput">
            <button @click="addFriend">Add Friend</button>
        </div>
    </div>
</template>

<script>
    import {bus} from '../../main.js'
    export default {
        data(){
            return{
                friendInput:''
            }
        },
        props:{
            userName: String,
            userLastName:String,
            userAge:Number,
            userParents:Object,
            updateLastName:Function
        },
        methods:{
            updateName(){
              //  this.userName = "Abul Hasan";
                this.$emit('updateName','Abul Hasan')
            },
            addFriend(){
                bus.$emit('addFriend',this.friendInput)
            }
        },
    }
</script>

<style>
    span{
        font-weight:800;
    }

    .user_profile{
        border:1px solid #2196F3;
        padding: 10px 20px;
        
    }
</style>