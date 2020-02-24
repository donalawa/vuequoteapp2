<template>
    <div class="col-md-4 col-lg-3">
     <div class="card card-default">
         <div class="card-body quote" v-bind:style="{ 'background-image': 'url(' + images[Math.ceil(Math.random() * images.length - 1)].foodImg + ')', backgroundSize: 'cover'}">
             <div class="mt content">
                <span class="content-text"><slot  name="content"></slot></span>
                      <br>
               <span class="sub"> <slot name="sub-title"></slot></span>
             </div> 
         </div>
     </div>
    </div>
</template>


<script>
import food from '../assets/images/food.jpg';
import karli from '../assets/images/karli.jpg';
import class1 from '../assets/images/class1.jpg'
export default {
    name: 'quote',
    data() {
        return {
           images: [
               {foodImg: food},
               {foodImg: karli},
               {foodImg: class1}
           ]
        }
    }
  }
</script>

<style>

 .card-body {
        font-family: Arial, Helvetica, sans-serif;
        font-size: 24px;
        color: teal;
    }
    .quote {
        cursor: pointer;
    }
    .quote:hover {
        background: #ffe2e2;
    }

    .card {
        height: 200px !important;
        display: flex !important;
        text-align: center;
        margin-bottom: 10px;
        box-shadow: 7px 10px 12px -5px rgba(0, 0, 0, 0.56);
    }

    .mt {
        padding-top: 40px;
    }

    .sub {
        font-size: 14px;
        color: red !important;
        background-color: white;
    }
.content {
    background-color:  white;
}

.content-text {
    font-size: 18px;
}
</style>