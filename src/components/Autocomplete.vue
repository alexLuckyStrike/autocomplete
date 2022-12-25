<template>
    <div class="autocomplete">
        <div class="input" >
            <div class="popover">
                     <input type="text"
                     v-model="query"
                     placeholder="Start Typing..."
                     >  
                     <div class="options">
                         <ul>
                             <li 
                             v-for="(match,index) in matches"
                             :key="index"
                               @click="itemClicked(index)">
                             
                               </li>
                         </ul>
                    </div>     
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:['items','filterby'],
    data(){
        return{
            query:'',

            visible:false
        };
    },

    methods:{
    
        itemClicked(index){

            console.log(index)

        }    
      },

     computed:{

         matches(){

             if(this.query == ''){
                 
                 return [];

            }  

            return this.items.filter((item)=> item.includes(this.query)) 

         }
       }   
    }

</script>


<style scoped>
.autocomplete{
    width:100%;
    position:relative;
}
.input {
    height: 40px;
    border-radius: 3px;
    border: 2px solid lightgray;
    box-shadow: 0 0 10px #eceaea;
    font-size: 25px;
    padding-left: 10px;
    padding-top: 10px;
    cursor: text;
}
</style>