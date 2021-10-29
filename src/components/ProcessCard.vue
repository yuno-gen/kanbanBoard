<template>
  <q-card class=" process-card bg-indigo-1" flat>
    <q-card-section class="text-h6 text-capitalize q-pb-none">
      {{ process.name }}
    </q-card-section>
    <div class="q-pt-none">
      <q-scroll-area style="height: 70vh; max-width: 380px" >
          <div class="q-gutter-md q-pa-md">
               <div v-for="job in process.jobs" :key="job.id" >
                    <Job :job="job" :pid="process.id" />
                </div>

          </div>
       
        <q-card-actions>
          <q-icon name="eva-plus-outline" size="20px" />
          <q-btn @click="showAddJob = true" flat no-caps> Add task... </q-btn>
        </q-card-actions>
      </q-scroll-area>
    </div>
    <JobAddDialog
      @closeDialog="showAddJob = false"
      :showAddJob="showAddJob"
      :pid="process.id"
    />
  </q-card>
</template>

<script>
import Job from "./Job.vue";
import JobAddDialog from "./JobAddDialog.vue";
export default {
  props: {
    process: {
      type: Object,
      default: null,
    },
  },
  components: {
    Job,
    JobAddDialog,
  },
  data() {
    return {
      showAddJob: false,
    };
  },
};
</script>

<style lang="scss">
.process-card {
  min-width: 350px;
  min-height: 400px;
}
</style>