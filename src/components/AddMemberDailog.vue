<template>
  <q-dialog v-model="showAddMember" persistent>
      <q-card class="addjob" style="border-radius: 20px;">
        <q-card-section class="bg-info">
          <div class="text-subtitle1 ">Add Job</div>
        </q-card-section>

        <q-card-section>
            <div class="subtitle1">Enter Member Name:</div>
                <q-input
                placeholder="Name"
                v-model="member.name"
                ref="fname"
                :rules="[val=> !!val || 'Field is Required']"
                outlined
                />
            
            <div class="subtitle1">Enter Img URL</div>
                <q-input
                    placeholder="Img URL"
                    v-model="member.imgUrl"
                    ref="fname"
                    :rules="[val=> !!val || 'Field is Required']"
                    outlined
                    />
        </q-card-section>

        <q-card-actions align="right" class="bg-info">
          <q-btn
                flat
                label="Cancel"
                color="primary"
                @click="$emit('closeDialog')" />
            <q-btn
                flat
                label="Save"
                color="primary"
                @click="addMember" />
        </q-card-actions>
      </q-card>
    </q-dialog>
</template>

<script>
import { uid } from 'quasar'
import { date } from 'quasar'
export default {
    props:{
        showAddMember:{
            type:Boolean,
            default:false
        },
        pid:{
            type:String,
            default:null
        },
        id:{
            type:String,
            default:null
        }
    },
    data(){
        return{
           member:{
                name:'',
                imgUrl: ''
            }
        }
    },
    methods:{
        addMember(){
            this.$emit('closeDialog')
            let payload = {
                id: this.id,
                pid: this.pid,
                member: this.member
            }
            this.$root.$emit('addMember', payload)
        },
        color(){
            let colors=[ "pink","deep-purple", "amber", "teal", "cyan-10", "lime-10","brown","blue-grey","deep-orange","green"];
            let i = Math.floor(Math.random()*6);
            return colors[i]
        }
    }

}
</script>

<style lang='scss'>
.addjob{
    border-radius: 20px;
}
</style>