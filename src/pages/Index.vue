<template>
  <q-page class="bg-indigo-1 page">
    
      <jobProcessWrapper :processes="processes" />
    
  </q-page>
</template>

<script>
import jobProcessWrapper from "src/components/JobProcessWrapper.vue";
export default {
  name: "PageIndex",
  data() {
    return {
      processes: [
        {
          id: '1',
          name: "Sprint #1",
          description:
            " simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industrys standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.",
          jobs: [
            {
              id: '1',
              name: "JS Hint implementation",
              caption: "simply dummy text of the printing",
              tags: [
                { name: "Discovery", color: "negative" },
              ],
              members: [
                "https://cdn.quasar.dev/img/avatar.png",
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
                  value: "04/04/2020",
                },
              ],
            },
            
            {
              id: '2',
              name: "Dashboard improvements",
              caption: "simply dummy text of the printing",
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
                  value: "04/04/2020",
                },
              ],
            },
            
          ],
        },
        {
          id: '2',
          name: "Sprint #2",
          description:
            " simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industrys standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.",
          jobs: [
            {
              id: '1',
              name: "Code migration and merge",
              caption: "simply dummy text of the printing",
              tags: [
                { name: "Development", color: "accent" },
                { name: "Support", color: "negative" },
              ],
              members: [
                "https://cdn.quasar.dev/img/avatar.png",
                "https://cdn.quasar.dev/img/avatar.png",
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
                  value: "04/04/2020",
                },
              ],
            },
            {
              id: '2',
              name: "Request Customer Feedback",
              caption: "simply dummy text of the printing",
              tags: [
                { name: "Development", color: "accent" },
              ],
              members: [
                "https://cdn.quasar.dev/img/avatar.png",
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
                  value: "04/04/2020",
                },
              ],
            },
            {
              id: '3',
              name: "CSS refactoring",
              caption: "simply dummy text of the printing",
              tags: [
                { name: "Support", color: "warning" },
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
                  value: "04/04/2020",
                },
              ],
            },
            
          ],
        },
        {
          id: '3',
          name: "Sprint #3",
          description:
            " simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industrys standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.",
          jobs: [
            {
              id: '1',
              name: "Request Customer Feedback",
              caption: "simply dummy text of the printing",
              tags: [
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
                  value: "04/04/2020",
                },
              ],
            },
            {
              id: '2',
              name: "Template translation",
              caption: "simply dummy text of the printing",
              tags: [
                { name: "Development", color: "accent" },
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
                  value: "04/04/2020",
                },
              ],
            },
            
          ],
        },
        {
          id: '4',
          name: "Sprint #4",
          description:
            " simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industrys standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.",
          jobs: [
            {
              id: '1',
              name: "Email Newsletter",
              caption: "simply dummy text of the printing",
              tags: [
                { name: "Support", color: "warning" },
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
                  value: "04/04/2020",
                },
              ],
            },
            
          ],
        },
        {
          id: '5',
          name: "Sprint #5",
          description:
            " simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industrys standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.",
          jobs: [
            {
              id: '1',
              name: "Code migration and merge",
              caption: "simply dummy text of the printing",
              tags: [
                { name: "Development", color: "accent" },
                { name: "Support", color: "negative" },
              ],
              members: [
                "https://cdn.quasar.dev/img/avatar.png",
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
                  value: "04/04/2020",
                },
              ],
            },
          ],
        },
      ],
    };
  },
  components: {
    jobProcessWrapper,
  },
  methods:{
    addJob(payload){
      this.processes.forEach(process=>{
        if(process.id==payload.pid){
          process.jobs.push(payload.job)
        }
      })
    },
    addMember(payload){
      this.processes.forEach(process=>{
        if(process.id==payload.pid){
            process.jobs.forEach(job=>{
              if(job.id==payload.id){
                job.members.push(payload.member.imgUrl)
              }
            })
        }
      })
    }
  },
  created(){
    this.$root.$on('addJob', this.addJob )
    this.$root.$on('addMember', )
  },
  destroyed(){
    this.$root.$off('addJob')
  }
};
</script>
<style lang="scss">
.page{
  height: 70vh;
}
</style>
