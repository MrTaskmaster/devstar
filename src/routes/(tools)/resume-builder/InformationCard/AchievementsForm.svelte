<script lang="ts">
  import { achievementStore } from "./AchievementStore";
  let achievements={achievementName :" ", achievementLink: " "}
  export let onCancel: () => void;
  export let idtoadd: number;
  function formSubmit(){
    onCancel();
    if(idtoadd === -1){
      achievementStore.update(items => {
        return [...items, {id: $achievementStore.length, achievementName: achievements.achievementName, achievementLink: achievements.achievementLink}];
      });
    }
    // else if(idtoadd > -1){
    //   $achievementStore[idtoadd].achievementName = achievements.achievementName;
    //   $achievementStore[idtoadd].achievementLink = achievements.achievementLink;
    // }
    console.log($achievementStore.length);
  }
</script>
<div class="form-upper">
  <div class="form-container">
    <form on:submit|preventDefault={formSubmit} id="projectform" >
      <div class="text-left text-xl font-bold">Achievements Details</div>
      
      <div class="flex-grow sm:mt-8">
        <label for="projectdesc" class="mb-1 block font-bold text-gray-900">Description</label>
        {#if idtoadd >-1}
          <textarea id="projectdesc" name="projectdesc" class="w-full rounded-xl border border-gray-600 px-3 py-2" rows="2" bind:value="{$achievementStore[idtoadd].achievementName}" placeholder="Enter your description" required></textarea>
        {:else}
          <textarea id="projectdesc" name="projectdesc" class="w-full rounded-xl border border-gray-600 px-3 py-2" rows="2" bind:value="{achievements.achievementName}" placeholder="Enter your description" required></textarea>
        {/if}
      </div>
      <div class="flex-1">
        <div class="ml-4 flex-grow-0 sm:ml-0">
          <label for="projectlink" class="mb-1 block font-bold text-gray-900">Link (Optional)</label>
          {#if idtoadd >-1}
            <input type="text" id="projectlink" name="projectlink" class="w-full rounded-xl border border-gray-600 px-3 py-2" bind:value="{$achievementStore[idtoadd].achievementLink}" placeholder="Enter project link" />
          {:else}
            <input type="text" id="projectlink" name="projectlink" class="w-full rounded-xl border border-gray-600 px-3 py-2" bind:value="{achievements.achievementLink}" placeholder="Enter project link" />
          {/if}
        </div>
      </div>
      <div class="mt-6 flex justify-end sm:mt-8">
        <button on:click={onCancel} type="button" id="closebutton" class="mr-4 px-4 py-2 font-thin text-black">Close</button>
        <button type="submit" class="rounded-lg border border-gray-800 bg-gray-900 p-1 px-6 py-2 font-thin text-white">Done</button>
      </div>
    </form>
  </div>
</div>
<style>
  .form-upper {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1;
    backdrop-filter: blur(3px);
  }
  .form-container {
    background-color: white;
    max-width: 600px;
    padding: 20px;
    border-radius: 10px;
    /* box-shadow: 0 25px 50px -12px rgba(99, 99, 99, 0.25); */
  }
</style>