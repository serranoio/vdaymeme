<script lang="ts">
import me from "./assets/me.jpg"
let yesChosen = false;
let noChosen = false; 
let noButton: HTMLButtonElement;

const submitForm = (e) => {
e.preventDefault();

  if (e.submitter.id == "yes") {
    yesChosen = true;
  }
  if (e.submitter.id == "no") {
let newWidth =   Math.random() * 100; 
let newHeight =   Math.random() * 100;

console.log(newHeight)
console.log(newWidth)
noButton.style.position = "absolute";

noButton.style.left = `calc(${newWidth}% - 70px)`
noButton.style.top = `calc(${newHeight}% - 70px)`
  }
}

if (noChosen) {
  noChosen = false;
}

</script>

<main>


  <div class="card">
      <form on:submit={submitForm}>


        <h1>Will u be my valentine?</h1>
    
        <div class="img-box">

          <img src={me} alt="sexy pic of me"/>
        </div>
        {#if !yesChosen}
        <div class="button-div">
        <button class="yes" id="yes" type="submit">Yes</button>
<button bind:this={noButton} class="no" id="no" type="submit">No</button> 
</div>
 {:else} 
 <div class="number">
   <p>Here's my number sweetheart</p>
   <p>630-303-8467</p>
  </div>
{/if}
      </form>
  </div>

</main>

<style>
.img-box {
  margin-top: 1.2rem;
  display: flex;
  justify-content: center;
  height: 35rem;
}
img {

  height: 100%;
}

.number {
  margin-top: 2.4rem;
  font-size: var(--fontSizeXLarge);
  text-align: center;
  color: var(--alertColorL40);
}

button:hover {
background-color: var(--errorColorL30);
color: var(--errorColorD30);
}
button {
  transition: all .2s;
  cursor: pointer;
padding: var(--spacing);
border: none;
background-color: var(--errorColorD30);
color: var(--errorColorL30);
}

.yes {
  font-size: var(--fontSizeXXLarge);
}

.no {
  font-size: var(--fontSizeXXLarge);
}

.button-div {
  margin-top: 2.4rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

main {
  background-color: var(--errorColorD40);
  width: 100vw;
  height: 100lvh;
  display: flex;
  align-items: center;
  justify-content: center;
}
.card {
  padding: 2.4rem;
}

h1 {
  color: var(--alertColorL30);

  text-align: center;

  font-size: var(--fontSizeXXLarge);
}


</style>
