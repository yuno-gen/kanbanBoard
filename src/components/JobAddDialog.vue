<template>
  <q-dialog v-model="showAddJob" persistent>
      <q-card class="addjob" style="border-radius: 20px;">
        <q-card-section class="bg-info">
          <div class="text-subtitle1 ">Add Job</div>
        </q-card-section>

         <q-card-section>
          <div>
            <div class="subtitle1">Enter Job Name:</div>
            <q-input
              placeholder="Enter Job"
              v-model="job.name"
              ref="fname"
              :rules="[val=> !!val || 'Field is Required']"
              outlined
              @input="$emit('update:student', $event)"
            >
            </q-input>
          </div>
          <div>
            <div class="subtitle1">Date:</div>
                <q-input filled v-model="job.subDetails[2].value"  :rules="['date']">
                    <template v-slot:append>
                        <q-icon name="event" class="cursor-pointer">
                        <q-popup-proxy ref="qDateProxy" transition-show="scale" transition-hide="scale">
                            <q-date
                              color="orange"
                              minimal
                              v-model="job.subDetails[2].value">
                            <div class="row items-center justify-end">
                                <q-btn v-close-popup label="Close" color="primary" flat />
                            </div>
                            </q-date>
                        </q-popup-proxy>
                        </q-icon>
                    </template>
                </q-input>
          </div>
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
                @click="save" />
        </q-card-actions>
      </q-card>
    </q-dialog>
</template>

<script>
import { uid } from 'quasar'
import { date } from 'quasar'
export default {
    props:{
        showAddJob:{
            type:Boolean,
            default:false
        },
        pid:{
            type:String,
            default:null
        }
    },
    data(){
        return{
           job:{
               id: '',
                name: "",
                tags: [
                    { name: "Development", color: "accent" },
                    { name: "Design", color: "positive" },
                ],
                members: [
                    "https://cdn.quasar.dev/img/avatar.png",
                    "https://cdn.quasar.dev/img/avatar.png",
                ],
                subDetails: [
                    {
                    name: "eva-file-outline",
                    value: 2,
                    },
                    {
                    name: "eva-message-square-outline",
                    value: 6,
                    },
                    {
                    name: "eva-calendar-outline",
                    value: "",
                    },
                ],
           }
        }
    },
    methods:{
        check(){
            if(job.name=='' || job.subDetails[2].value=='')
                return false
            return true
        },
        save(){
            let jobDate = this.job.subDetails[2].value
            jobDate = date.formatDate(jobDate, 'DD/MM/YYYY')
            this.job.id=uid()
            this.job.subDetails[2].value=jobDate
            this.$emit('closeDialog')
            let payload={
                pid: this.pid,
                job: this.job
            }
            this.$root.$emit('addJob', payload)
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