<template>
  
      <q-scroll-area
        horizontal
        style="height: 85vh; width: 95vw"
      >
      <div class="gt-xs">
        <div class="no-wrap row q-ma-md">
            <div v-for="process in processes" :key="process.id">
                <processCard :process="process"/>
                <q-separator color="black" size="10px" vertical />
            </div> 
        </div>
      </div>
      <div class="lt-sm">
          <div class="column">
            <div v-for="process in processes" :key="process.id">
                <q-expansion-item
                  :label="process.name"
                  icon="eva-checkmark-circle-outline"
                  class="bg-secondary q-mt-md"
                  style="width: 95vw; border-radius: 30px">
                    <processCard :process="process"/>
                </q-expansion-item>
                
            </div> 
        </div>
      </div>

      </q-scroll-area>
  
</template>

<script>
import processCard from './ProcessCard.vue'
export default {
    props:{
        processes:{
            type: Array,
            default: null
        }
    },
    components:{
        processCard
    },
    mounted(){
        console.log('mounted');
    }
}
</script>

<style>

</style>