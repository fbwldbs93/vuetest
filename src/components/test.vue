<template>
    <div id="app">
        <h1>{{ test }}</h1>
        <h1>{{ test2 }}</h1>
    </div>
</template>

<script>
export default {
    /*
    name: 'Test',
    props: {
        msg: {
            type:String
        }
    }
    */
   data(){
       return {
           test : "hello", 
           test2 : "bye"
       }
   },
   
}
</script>