<script>
  import SkillsForm from "./skillsForm.svelte";
  let isEditing = false;
  function toggleForm(){
    isEditing = !isEditing;
  }
</script>
<div class="flex items-center justify-between p-4">
    <div class="flex items-center">
      <div class="rounded-full bg-gray-400 dark:bg-white p-4">
        <span>
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="h-6 w-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M11.42 15.17L17.25 21A2.652 2.652 0 0021 17.25l-5.877-5.877M11.42 15.17l2.496-3.03c.317-.384.74-.626 1.208-.766M11.42 15.17l-4.655 5.653a2.548 2.548 0 11-3.586-3.586l6.837-5.63m5.108-.233c.55-.164 1.163-.188 1.743-.14a4.5 4.5 0 004.486-6.336l-3.276 3.277a3.004 3.004 0 01-2.25-2.25l3.276-3.276a4.5 4.5 0 00-6.336 4.486c.091 1.076-.071 2.264-.904 2.95l-.102.085m-1.745 1.437L5.909 7.5H4.5L2.25 3.75l1.5-1.5L7.5 4.5v1.409l4.26 4.26m-1.745 1.437l1.745-1.437m6.615 8.206L15.75 15.75M4.867 19.125h.008v.008h-.008v-.008z" />
          </svg>
        </span>
      </div>
      <div class="ml-2">
        <h1 class="inline text-base font-medium text-gray-900 dark:text-white">Add Skills</h1>
        <p class="text-sm text-gray-700 dark:text-gray-400">Your Skills</p>
      </div>
    </div>
  
    <div class="flex items-center">
      <button on:click={toggleForm} class="flex items-center rounded-lg border-2 border-gray-900 dark:border-white bg-transparent px-6 py-2 text-lg font-semibold text-gray-900 dark:text-white">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="h-6 w-6">
          <path fill-rule="evenodd" d="M12 5.25a.75.75 0 01.75.75v5.25H18a.75.75 0 010 1.5h-5.25V18a.75.75 0 01-1.5 0v-5.25H6a.75.75 0 010-1.5h5.25V6a.75.75 0 01.75-.75z" clip-rule="evenodd" />
        </svg>
        Add
      </button>
    </div>
  </div>
{#if isEditing}
  <SkillsForm onCancel={toggleForm}/>
{/if}