<template>
    <div class="area">
        
        <form class="col s12">
            <div class ="row"> 
                <!-- temp input  -->
                <div class ="input-field col s3">     
                    <input id='temp' type='number' class='validate' />
                    <label for ='temp'> Temperature... </label>                 
                </div>

                <!-- Hum input  -->
                <div class ="input-field col s3">     
                    <input id='hum' type='number' class='validate' />
                    <label for ='hum'> Humanity... </label>                 
                </div>

                <!-- pot input  -->
                <div class ="input-field col s3">     
                    <input id='pot' type='number' class='validate' />
                    <label for ='pot'> Potentio... </label>                 
                </div>

                <div class ="col s3">
                    <div class ="row">
                        <a class="col s6 waves-effect waves-light btn-large teal lighten-2">
                            <i class="material-icons">cloud_download</i>
                        </a>
                          <a class="col s6 waves-effect waves-light btn-large pink lighten-2">
                            <i class="material-icons">cloud_upload</i>
                        </a>
                    </div>   
                </div>
            </div>
        </form>
        <LineChart :chart-data= "datacollection"> </LineChart>
    </div>
</template>

<script>
import LineChart from './line.js'

export default {
    components: {

        LineChart 
    },
    data(){
        return{
            datacollection:null,
            loaded:false

        }
    },
    
    mounted(){
            this.fillData()

    },
        
    methods:{
            fillData(){
                this.datacollection ={
                    labels: [0,1,2,3,4,5,6,7,8,9],
                    datasets:[
                        {
                            label: 'Temp',
                            backgroundColor: 'rgba(255,0,0,0.2)',
                            borderColor:'lightblue',
                            pointBackgroundColor: 'blue',
                            borderWidth: 1,
                            pointBorderColor: 'blue',
                            data: [0,1,3,3,4,5,6,7,8,9]
                        }
                    ]
                }
            


        }
    }
    
}
</script>


<style scoped>
.area{
width: 500px;
height: 200px;
margin: auto;
}


</style>