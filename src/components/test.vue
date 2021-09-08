<template>
    <h1>hi,vue</h1>
    <!--<p>{{filteredBooks}}</p>-->
    <div v-if="showBooks">
        <!--
        <p>{{ books[0].title }} - {{ books[0].author }}</p>
        <p>{{ books[1].title }} - {{ books[1].author }}</p>
        <p>{{ books[2].title }} - {{ books[2].author }}</p>
        -->
        <!-- attribute binding -->
        <a v-bind:href="url">english learning blog</a>
        <ul>
            <li v-for="book in filteredBooks" v-bind:key="book" v-bind:class="{fav : book.isFav}" @click="toggleFav(book)">
                <!--
                    컴포넌트에서 v-for을 사용할 때, key 값이 요구됨.
                    v-bind:key="book"을 추가해주기
                -->
                <img :src="book.img" :alt="book.title"/>
                <h3>{{book.title}}</h3>
                <p>{{book.author}}</p>
            </li>
        </ul>
        <button v-on:click="age++">Increase age</button>
        <button v-on:click="age--">decrease age</button>
        <div v-on:click="changeTitle('ants')">change book title</div>
    </div>

    <button v-on:click="toggleShowBooks">
        <span v-if="showBooks">Hide books</span>
        <!--<span v-if="!showBooks">show books</span>-->
        <span v-else>show books</span>
    </button>

    <div v-show="showBooks">currently showing books</div>

    <br/>

    <!-- mouse events -->

    <div class="box" v-on:mouseover="handleEvent">mouseover (enter)</div>
    <div class="box" v-on:mouseleave="handleEvent">mouseleave</div>
    <div class="box" v-on:dblclick="handleEvent">double click</div>
    <div class="box" v-on:mousemove="handleMousemove">position = {{ x }},{{ y }}</div>

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
   name : "app",
   data(){
       return {
           url: 'https://blog.daum.net/rheesahn54/1837',
           showBooks : true,
           title : "The Final Empire",
           author : "Brandon Sanderson",
           age : 45,
           x : 0,
           y : 0,
           books : [
               {
                   title : 'name of the wind', author : 'patrick rothfuss', img : require('../assets/book1.jpeg'), isFav : true
               },
               {
                   title : 'the way of kings', author : 'brandon sanderson', img : require('../assets/book2.jpeg'), isFav : false
               },
               {
                   title : 'the final empire', author : 'brandon sanderson', img : require('../assets/book3.jpeg'), isFav: true
               }
           ]
       }
   },
   methods:{
       changeTitle(title){
           //this.title = "words of Randiance"
           this.title = title
       },
       toggleShowBooks(){
           this.showBooks = !this.showBooks
       }, 
       handleEvent(e){
           console.log(e, e.type)
       }, 
       handleMousemove(e){
           this.x = e.offsetX
           this.y = e.offsetY
       }, 
       toggleFav(book){
           book.isFav = !book.isFav
       }
   },
   computed:{
       filteredBooks(){
           return this.books.filter((book)=> book.isFav )
       }
   }
   
}
//Challenge - Add to Favs
// - attach a click event to each li tag (for each book)
// - when a user clicks an li, toggle the 'isFav' property of that book



</script>

<style>
    *{
        padding:0;
        margin:0;
    }
    body{
        background:#eee;
        max-width:960px;
        margin:20px auto;
    }
</style>

<style scoped>
    p, h3, ul{
        margin:0;
        padding:0;
    }
    li{
        list-style:none;
        background:#fff;
        margin:20px auto;
        padding:10px 20px;
        border-radius:10px;
        display:flex;
        align-items:center;
        justify-content:space-between;
        cursor:pointer;
    }

    li.fav{
        background:pink;
        color:#fff;
    }
    .box{
        padding:50px 0;
        width:150px;
        text-align:center;
        background:#ddd;
        margin:20px;
        display:inline-block;
        border-radius:10px;
        cursor:pointer;
    }

    img{
        width:100px;
    }
</style>