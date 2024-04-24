<template>
    <div class="container">
        <h2 class="item-name">{{item.item_name}}</h2>
        <p>Brand : {{item.item_brand}}</p>
        <p>Price : ${{item.item_price}}</p>
        <p>Series : {{item.item_series}}</p>
        <p>Rating : <span class="rating"><img src="https://img.icons8.com/?size=32&id=43879&format=png" class="star"/>&nbsp;{{item.item_rating}}</span></p>
        <p>Review : {{item.item_review}}</p>
        <p>Discount : {{item.item_discount}}</p>
        <p>Original Price : ${{item.item_originalPrice}}</p>
        <p>Delivery Charges: {{item.item_deliveryCharges}}</p>
    </div>
</template>

<script>
    export default{
        name:"ElectronicItem",
        props:{
            item:Object
        }
    }
</script>

<style scoped>
    .container{
        border-top: 5px solid #6b9080;
        padding:1em;
        box-shadow:0 4px 8px 0 rgba(0,0,0,0.2),0 6px 20px 0 rgba(0,0,0,0.19);
        font-size: 1em;
    }
    .item-name{
        color: #6b9080;
    }
    .rating .star{
        width:16px;
        height:16px;
        vertical-align: middle;
    }
    .rating{
        border: transparent;
        border-radius:20px;
        background-color:#9fc1b3;
        padding: 6px;
        text-align: center;
        vertical-align: middle;
    }
</style>