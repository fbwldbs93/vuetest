<template>
    <div class="backdrop">
        <div class="modal">
            <h1>{{ header }}</h1>
            <p>{{ text }}</p>
        </div>
    </div>
</template>

<script>
export default {
    //https://beomy.tistory.com/56
    //props 에 관한 좋은 설명
    props: ['header','text'],
    data() {
        return {
            title: ''
        }
    }
}
</script>

<style scoped>
    .modal {
        width:400px;
        padding:20px;
        margin:100px auto;
        background: white;
        border-radius:10px;
    }
    .backdrop {
        top:0;
        position:fixed;
        background:rgba(0,0,0,0.5);
        width:100%;
        height:100%;
    }
    .modal h1 {
        color:#03cfb4;
        border:none;
        padding:0;
    }

    .modal p {
        font-style:normal;
    }
</style>