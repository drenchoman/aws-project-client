<script>
  import q from '../assets/question.svg'
  import FeedbackHelp from './FeedbackHelp.svelte'
 import { feedbackVisible } from './Stores';

function handleClick(){
  feedbackVisible.set(!$feedbackVisible)
}


</script>



    <div on:click={handleClick} class="help">
      <span>Need help?</span>
      <img src={q} alt="Help me" />
    </div>



<style>
  .help{
    display: flex;
    flex-direction: column-reverse;
    justify-content: center;
    align-items: center;
  }
  .help > *{
    margin: 0.25rem 0.25rem;
  }

  .help:hover{
    cursor: pointer;
    text-decoration: underline;
  }
</style>