<script>
  import AchievementsForm from "./AchievementsForm.svelte";
  let isEditing=false
  function toggleForm()
  {
    isEditing=!isEditing;
  }
</script>

<div class="flex items-center justify-between p-4">
    <div class="flex items-center">
      <div class="rounded-full bg-gray-400 dark:bg-white p-4">
        <span>
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="h-6 w-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M16.5 18.75h-9m9 0a3 3 0 013 3h-15a3 3 0 013-3m9 0v-3.375c0-.621-.503-1.125-1.125-1.125h-.871M7.5 18.75v-3.375c0-.621.504-1.125 1.125-1.125h.872m5.007 0H9.497m5.007 0a7.454 7.454 0 01-.982-3.172M9.497 14.25a7.454 7.454 0 00.981-3.172M5.25 4.236c-.982.143-1.954.317-2.916.52A6.003 6.003 0 007.73 9.728M5.25 4.236V4.5c0 2.108.966 3.99 2.48 5.228M5.25 4.236V2.721C7.456 2.41 9.71 2.25 12 2.25c2.291 0 4.545.16 6.75.47v1.516M7.73 9.728a6.726 6.726 0 002.748 1.35m8.272-6.842V4.5c0 2.108-.966 3.99-2.48 5.228m2.48-5.492a46.32 46.32 0 012.916.52 6.003 6.003 0 01-5.395 4.972m0 0a6.726 6.726 0 01-2.749 1.35m0 0a6.772 6.772 0 01-3.044 0" />
          </svg>
        </span>
      </div>
      <div class="ml-2">
        <h1 class="inline text-base font-medium text-gray-900 dark:text-white">Add Achievements Details</h1>
        <p class="text-sm text-gray-700 dark:text-gray-400">Your Achievements</p>
      </div>
    </div>
  
    <div class="flex items-center">
      <button on:click={toggleForm} class="flex items-center rounded-lg border-2 border-2 border-gray-900 dark:border-white bg-transparent px-6 py-2 text-lg font-semibold text-gray-900 dark:text-white">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="h-6 w-6">
          <path fill-rule="evenodd" d="M12 5.25a.75.75 0 01.75.75v5.25H18a.75.75 0 010 1.5h-5.25V18a.75.75 0 01-1.5 0v-5.25H6a.75.75 0 010-1.5h5.25V6a.75.75 0 01.75-.75z" clip-rule="evenodd" />
        </svg>
  
        Add
      </button>
    </div>
  </div>
  {#if isEditing}
<AchievementsForm onCancel={toggleForm} idtoadd={-1}/>
{/if}

 