<script>
import {ids, counter} from './Stores'
const getRandomId = () => {
    return ids[Math.floor(Math.random()*DataTransferItemList.length)]
  }
const url = `http://localhost:5000/feedback/${getRandomId()}`


const getFeedback = async () => {
  let res = await fetch(url)
  let data = await res.json()
  let qNum = 'q' + $counter
  return data[qNum]
}
let feedbackPromise = getFeedback()
</script>

<div>
  {#await feedbackPromise}
  <h2>Loading...</h2>
  {:then feedback}
  <div>
    <h3>Here is how someone else answered</h3>
    <p>{feedback}</p>
  </div>
  {:catch err}
  <h2>Error while laoding the data</h2>
  {/await}
</div>