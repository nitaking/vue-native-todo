<template>
    <view class="container">
        <text-input class="text-input" v-model="newText" />
        <touchable-opacity class="button" :on-press="addTodo">
            <text class="button-text">追加</text>
        </touchable-opacity>
    </view>
</template>

<script>
    export default {
        name: 'text-inputs',
        props: {
            onAdd: Function
        },
        methods: {
          addTodo: function() {
            this.onAdd(this.newText);
            console.log("addTodo",this.newText);
          },
        }
    }
</script>

<style>
.container {
    flex-direction: row;
    padding: 20px;
}
.text-input {
    background-color: white;
    margin-right: 5px;
    flex: 3;
}
.button {
    flex: 1;
    background-color: #008080;
    margin-left: 5px;
    align-items: center;
    justify-content: center;
    padding-top: 10px;
    padding-bottom: 10px;
}
.button-text {
    color: white;
    font-weight: normal;
}
</style>