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

    </div>


    
    
    <compFooter/>
</div>
    
</template>

<script>
    import compFooter from './Components/Header_footer/Footer.vue';
    import compUserProfile from './Components/User/Profile.vue';
    import compFriends from './Components/User/Friends.vue';

    export default {
        data() {
            return {
                name:"Abul",
                lastname:"Hasan",
                age:24,
                parents:{
                    mother:"Nozufa",
                    father:"Shafikul"
                }
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
            compFriends
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