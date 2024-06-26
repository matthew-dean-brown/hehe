<template>
    <div :style="{
        backgroundImage: `url(${cover})`, 
        backgroundSize:'cover', 
        filter:'blur(4px)'
     }" >
        
    </div>
    <div><h1>
            This is the product component✌️
            <!-- {{ bookTitle}} -->
            <slot name="heading"></slot>
            <slot name="author"></slot>
            <slot name="pages"></slot>
            <slot></slot>
            
            <!-- <br>
            {{ bookTitle.title }}
            <br>
            {{ bookTitle.author }}
            <br>
            {{ bookTitle.year }}
            <br>
            {{ bookTitle.genre }}
            <br>
            {{ bookTitle.pages }}
            <br>
            {{ bookTitle.publisher }}
            <br>
            {{ bookTitle.isbn }} -->
        </h1></div>
</template>
<script>

export default {
    // props:['bookTitle']
    props:['cover']
    // props:{
    //     bookTitle:Object
    // }
}
</script>
<style>
    h1{
        color: #ffffff;
        text-shadow: 3px 3px black;
    }
    div{
        width: 300px;
        height: 400px;
        position: absolute;
        border-radius: 10%;
    }
</style>