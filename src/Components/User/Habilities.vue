<template>
    <div class="user_profile">
        <h3>User profile:</h3>
        
        <div>
            <slot name="main_hab"></slot>
        </div>
        <hr>
        <div>
            <slot name="notes"></slot>
        </div>
        <div>
            <slot></slot>
            <hr>
            <slot name="other">Loading.......</slot>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            habilities:['JS','CSS','HTML']
        }
    }
}
</script>
<style scoped>
    li{
        color: red;
    }
    .user_profile{
        border:1px solid #2196F3;
        padding: 10px 20px;
        
    }
</style>