<script>
  import { conversations } from "./data";
  // import { wordExplainPopup } from "/funcs.js";
  const start = 1;
  const chunkFromConversations = conversations.slice(start, start + 1);

</script>

<svelte:head>
  <title>conversations</title>
  <meta name="description" content="About this app" />
</svelte:head>

<section>
  <h1>محادثة اليوم</h1>

  <div id="en-lesson-conversations">
    {#each chunkFromConversations as [language1, language2]}
      <div class="conversation">
       
         {#each language1 as item1,i (language1.indexOf(item1)) }
         
         <div class="en-ar-div {i % 2 === 1 ? 'flexEnd' : ''}">
          
          <p class="en-sentence">{#each item1.split(" ") as word}
            <span class="en-word">{word}</span>
          {/each}</p>
          <p class="ar-sentence">{language2[i]}</p>
         </div>
         {/each}
       
      </div>
    {/each}
  </div>

  <div id="popupArrow" />
  <div id="popupBox" dir="auto" />
</section>
<style>

  .conversation{
     
      display: flex;
      flex-direction: column;
      gap: 50px;
      max-width:300px;
      margin: auto;
      color: white;
      
  }
  .en-ar-div{
      max-width: 200px;
      padding: 10px;
      border-radius: 15px;
      align-self:flex-start; 
      background-color:#333;
  }
  .en-ar-div.flexEnd{
  align-self:flex-end; 
  background-color:rgb(6, 16, 92);
 }
  .en-ar-div > p:nth-child(2){
     color: #999;
  }

  .en-ar-div > p{
      margin: 0;
  }

  
  
</style>