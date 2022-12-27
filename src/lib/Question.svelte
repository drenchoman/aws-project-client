<script>
import {q1, q2, q3} from './Stores'
import { fly, fade } from 'svelte/transition';
import Right from './Right.svelte';
export let question
export let qnum
const options = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
	let visible = true;
</script>

{#if qnum == 1}
<div in:fly="{{ y: 200, duration: 2000 }}" out:fly="{{ y: -200, duration: 800 }}" class="card">
  <div class="q">
    <div class='left'>
      <span>1.</span>
    </div>
    <div class='right'>
      <label for="q1">Great! {question}</label>
  <p>What need is it solving? How is it helping?</p>
  <input required placeholder="Type your answer here..." name='q1' id='#q1' type="text" bind:value={$q1}>
  <hr/>
  <Right />
    </div>
    
  </div>
  

 
</div>
{:else if qnum == 2}
<div in:fly="{{ y: 200, duration: 2000, delay: 800 }}" out:fly="{{ y: -200, duration:800 }}" class="card">
  <div class="q">
    <div class='left'>
      <span>2.</span>
    </div>
    <div class='right'>
      <label for="q2">{question}</label>
      <div class="numOptions">
        {#each options as num}
        <div class="num">
          <label >{num}
            <input required placeholder="Type your answer here..." name='q2' id='#q2' type="radio" value={num} bind:group={$q2}>
              </label>
        </div>
        
        {/each}
        </div>
      <hr/>
      <Right />
    </div>
  </div>
</div>
{:else if qnum == 3 }
<div in:fly="{{ y: 200, duration: 2000, delay: 800 }}" out:fly="{{ y: -200, duration:800 }}" class="card">
    <div class="q">
      <div class='left'>
        <span>3.</span>
      </div>
      <div class='right'>
  <label for="q3">{question}</label>
  <input required placeholder="Type your answer here..." name='q3' id='#q3' type="text" bind:value={$q3}>
  <hr/>
    <Right />
    </div>
  </div>
  
</div>
{/if}

<style>
  .card{
    display: flex;
    flex-direction: column;
    padding: 0 1rem;
  }
.left{
  margin-top: 0.5rem;
  margin-right: 1rem;
}

  .right > * {
    margin: 0.5rem 0;
  }
span{
  font-size: 0.8rem;


}
p{
  font-size: 1.3rem;
  font-weight: 400;
}

.right{
  text-align: left;
  display: flex;
    flex-direction: column;
}

.q{
  display: flex;
  flex-direction: row;
}

hr{
  width: 100%;
  border: 0px;
  border-bottom: 1px solid white;
}
input[type='radio'] {
  box-sizing: border-box;
  appearance: none;
  background: white;
  outline: 2px solid #333;
  border: 3px solid white;
  width: 16px;
  height: 16px;
}

input[type='radio']:checked {
  background: #333;
}

.numOptions{
  display: flex;
  flex-direction: row;
}

.num{
  display: flex;
  flex-direction: column;
}

.num > label {
  text-align: center;
}

@media screen and (max-width: 420px){
  .left{
    margin-right: 0.5rem;
  }
}
</style>