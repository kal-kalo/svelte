<script>
  import { oxford3000 } from "./data.js";
  import { wordExplainPopup } from "../../funcs.js";
  let lastVisited = parseInt(localStorage.getItem("oxford3000LastVisited")) || 0;
  let chunck;
  const currentDict = {};
  renderChunck(lastVisited, oxford3000);

  function renderChunck(indexStart, arr) {
    //const arr = array
     chunck = arr.slice(indexStart, indexStart + 2)
    
    // Iterate through the oxf array and merge the dict objects
    chunck.forEach((item) => {
      const dict = item.dict;
      for (const key in dict) {
        if (dict.hasOwnProperty(key)) {
          currentDict[key] = dict[key];
        }
      }
    });
  }
</script>

<div>
  <h1>Oxford 3000</h1>

  <button id="prev-btn" on:click={()=>{
    if (lastVisited <= 0) {
      lastVisited = oxford3000.length;
    }

    lastVisited--;

    localStorage.setItem("oxford3000LastVisited", lastVisited);
    renderChunck(lastVisited, oxford3000);
  }}>Previous</button>
  <button id="next-btn" on:click={()=>{
    if (lastVisited >= oxford3000.length - 1) {
      lastVisited = -1;
    }
    lastVisited++;

    localStorage.setItem("oxford3000LastVisited", lastVisited);
    renderChunck(lastVisited, oxford3000);
  }}>Next</button>
  <div id="english-lesson" class="todays-lesson">
    {#each chunck as item }
    <div class="entry">

        <div class="head">
            <h3>
                <span class="en-key en-word">{item.key}</span>
                <span class="ar-key" >{item.dict[item.key] || ''}</span>
            </h3>
            <p class="related">{item.related || ''}</p>
        </div>
        
        <ul class="body">
            {#if item.examples && item.examples.length > 0}
            {#each item.examples as example}
                <li>
                    <p class="en-sentence">
                   {#each example.enSentence.split(" ") as word}
                    <span class="en-word" on:click={e=>wordExplainPopup(e, currentDict)}>{word} </span>
                    
                   {/each}
                </p>
                   <p class="ar-sentence">{example.arSentence}</p>
                </li>
                
            {/each}
            
            {/if}
            
        </ul>
        
    </div>
    
    {/each}
  </div>

</div>

<style>
    #popupBox {
      position: absolute;
      background-color: darkgray;
      max-width: 2000px;
      border-radius: 5%;
      padding-top: 5px;
      padding-left: 10px;
      padding-right: 10px;
      padding-bottom: 15px;
      display: none;
    }

    #popupArrow {
      position: absolute;
      width: 0;
      height: 0;
      border-left: 8px solid transparent;
      border-right: 8px solid transparent;
      border-bottom: 8px solid darkgray;
      display: none;

    }
</style>