<script>
  import Nav from './lib/Nav.svelte';
  import Card from './lib/Card.svelte'
 import Question from './lib/Question.svelte';
 import {counter, q1, q2, q3, feedbackVisible} from './lib/Stores'
import FeedbackHelp from './lib/FeedbackHelp.svelte';


</script>
<Nav />
<main class='main'>

  <div class="card">
    {#if $counter == 0}
    <div>
      <h2>Hey there! We'd love to learn more about how our product is helping you.</h2>
      <p>Can you spare 3 minutes?</p>
      <Card /> 
    </div>
   {:else if $counter == 1}
     <Question question={'How exactly are you using our product?'} qnum={1} />
    {:else if $counter == 2 }
      <Question question={'How likely are you to recommend us to a friend or colleague?'} qnum={2}/> 
    {:else if $counter == 3}
      <Question question={'If you could change one thing about our product, what would it be?'} qnum={3} />
    {:else if $counter == 4}
    <Question question="N/A" qnum={4} /> 
   {/if}
    </div>

  
    {#if $feedbackVisible}
    <FeedbackHelp />
    {/if}

  

</main>

<style>

  main{
    width: 100%;
    height: 80vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  
  }

  .card{
    max-width: 525px;
    padding: 0 1rem;
  }
 
  @media screen and (max-width: 420px){
    .main{
      height: 80vh;
    }
  }


</style>
