<template>
    <view class='container'>
        <view class='left'>
            <!--<button :on-press="onDone">-->
                <!--{done? "Undo" : "Done"}-->
            <!--</button>-->
            <text class="text">{{text}}</text>
        </view>
        <!--<button-->
            <!--class="deleteButton"-->
            <!--:on-press="onDelete"-->
        <!--&gt;-->
            <!--Delete-->
        <!--</button>-->
    </view>
</template>

<script>
  export default {
    name: "TodoItem",
    props: {
      onDone: Number,
      onDelete: Number,
      text: String,
      item: Object,
    },
  }
</script>

<style scoped>
    .container {
        background-color:gray;
        padding-top: 10px;
        padding-bottom: 10px;
        padding-left: 5px;
        padding-right: 5px;
        margin-bottom: 10px;
        min-height: 50px;
        flex-direction: row;
        justify-content: space-between;
    }
    .text {
        color: #333;
    }
    .done-text {
        text-decoration-line: line-through;
    }
    .delete-button {
        background-color: #800000;
    }
    .left {
        flex-direction: row;
        align-items: center;
    }
</style>