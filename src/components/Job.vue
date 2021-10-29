<template>
  <q-card class=" job-card ">
   <q-card-section class="text-subtitle1 text-capitalize text-bold q-pb-none">
        {{ job.name }}
    </q-card-section>
   <q-item class="q-py-none" >
        <div v-for="details in job.subDetails" :key="details.id" class="row">
            <div class="q-gutter-x-sm  q-pr-md ">
                <q-icon :name="details.name" size="xs"/>
                <span>{{details.value}}</span>
            </div>
                
        </div>   
    </q-item>
    <div class="row justify-between q-pa-sm">
      <div class="row">
        <div v-for="tag in job.tags" :key="tag.id" class="q-pa-xs">
          <q-badge  :color="tag.color" class="q-pa-xs text-black text-caption">
                {{tag.name}}
              </q-badge>
        </div>
      </div>
            
        <div class="row q-gutter-sm " v-if="job.members.length<3">
          <div>
            <q-icon
              @click="showAddMember=true"
              name="eva-plus-circle-outline"
              size="30px" />
          </div>
            <div v-for="member in job.members"
                  :key="member.id"  >
               <q-avatar
                  size="30px">
                  <img :src="member">
                </q-avatar>
            </div>
        </div>

        <div class="row q-gutter-sm q-px-sm" v-else>
          <div>
            <q-icon
              @click="showAddMember=true"
              name="eva-plus-circle-outline"
              size="30px" />
              
          </div>
          <q-avatar
              size="30px">
              <img :src="job.members[0]">
            </q-avatar>
            <q-avatar
              size="30px">
              <img :src="job.members[1]">
            </q-avatar>
            <q-avatar color="secondary" text-color="white" size="30px">
              +{{job.members.length-2}}
            </q-avatar>
        </div>
        
        
    </div>
    <AddMemberDailog
      @closeDialog="showAddMember=false"
      :showAddMember="showAddMember"
      :pid="pid"
      :id="job.id" />
  </q-card>
</template>

<script>
import AddMemberDailog from './AddMemberDailog.vue'
export default {
  props: {
    job: {
      type: Object,
      default: null,
    },
    pid:{
      type: Number,
      default: null
    }
  },
  components:{
    AddMemberDailog
  },
  data(){
    return{
      showAddMember: false,
      
    }
  },
  
};
</script>

<style lang='scss'>
.job-card{
  height: 150px;
  min-width: 330px;
}
</style>