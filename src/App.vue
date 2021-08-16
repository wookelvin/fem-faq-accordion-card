<template>
  <Card >
    <h1>FAQ</h1>
    <div>
      <FAQItem v-for="(faqitem,index) of faq" :key="`faq${index}`" :q="faqitem.q" @clicked="showing = index" :show="showing === index">{{faqitem.a}}</FAQItem>
    </div>
  </Card>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Card from './components/Card.vue'
import FAQItem from './components/FAQItem.vue'

export default defineComponent({
  name: 'App', 
  components:{ 
    Card, 
    FAQItem
  }, 
  data: () => ({ 
    showing: 0,
    faq:[
      {
        q: 'How many team members can I invite?',
        a: 'You can invite up to 2 additional users on the Free plan. There is no limit on team members for the Premium plan.'
      },{
        q:'What is the maximum file upload size?',
        a:'No more than 2GB. All files in your account must fit your allotted storage space.'
      },{
        q:'How do I reset my password?',
        a:'Click “Forgot password” from the login page or “Change password” from your profile page. A reset link will be emailed to you.'
      },{
        q:'Can I cancel my subscription?',
        a:'Yes! Send us a message and we’ll process your request no questions asked.'
      },{
        q:'Do you provide additional support?',
        a:'Chat and email support is available 24/7. Phone lines are open during normal business hours.'
      }
    ]
  })
})
</script>

<style>
</style>
