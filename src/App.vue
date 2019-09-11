<template>
<div>
    <app-header></app-header>
    <div class="container">
        <compUserProfile
        :userName="name"
        :userLastName="lastname"
        :userAge="age"
        :userParents="parents"
        @updateName="name = $event"
        :updateLastName="updateLastName"
    />
    <compFriends/>
    <compHabilities>
        <ul slot="main_hab">
            <li v-for="(hab,index) in habilities" :key="index">
                {{hab}}
            </li>
        </ul>
        <div slot="notes">
            <p>The user also knows PHP</p>
        </div>
        <div>
            <a href="#">See more about this user</a>
        </div>
    </compHabilities>
    </div>

    <compFooter/>
</div>
    
</template>

<script>
    import compFooter from './Components/Header_footer/Footer.vue';
    import compUserProfile from './Components/User/Profile.vue';
    import compFriends from './Components/User/Friends.vue';
    import compHabilities from './Components/User/Habilities.vue';

    export default {
        data() {
            return {
                name:"Abul",
                lastname:"Hasan",
                age:24,
                parents:{
                    mother:"Nozufa",
                    father:"Shafikul"
                },
                habilities:['JS','CSS','HTML']
            }
        },
        methods:{
            updateLastName(value){
                this.lastname = value;
            }
        },
        
        components:{
            compFooter,
            compUserProfile,
            compFriends,
            compHabilities
        }
    }
</script>
<style>
    body{
        padding:0px;
        margin:0;
        font-family:'Roboto',sans-serif;
    }
    .container{
        min-height:84vh;
        box-sizing:border-box;
        padding:20px;
    }
    
</style>