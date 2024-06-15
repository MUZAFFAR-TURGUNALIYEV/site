<template>
    <div>
        <h3>
            {{ user.name }}

        </h3>
    <p>
        {{ user.pass }} - <b>{{ user.email }}</b>
    </p>
    </div>
</template>
<script>
export default{
    props: {
        user:{
            type:Object,
            ruquied:true
        }
    }
}
</script>