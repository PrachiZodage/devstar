<script lang="ts">

  import CForm from "./CForm.svelte";
  import { Certificationstore } from "./Certificationstore";
  export let idfordetail: number;
  let isEditing = false;

  function toggleForm()
  {
    isEditing = !isEditing;
  }
</script>

<div class="flex items-center justify-between rounded-2xl bg-gray-400 p-4 mb-2">
  <div>
    <h1 class="inline text-lg font-semibold">{$Certificationstore[idfordetail].title}<span class="text-base font-normal text-gray-500"> | <a href="{$Certificationstore[idfordetail].link}">Link</a></span></h1>
  </div>
  <div class="flex items-center">
    <button on:click={toggleForm} class="flex items-center rounded-xl border-2 border-gray-800 p-1 pl-3 pr-3 font-medium">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="mr-2 h-4 w-4">
        <path d="M21.731 2.269a2.625 2.625 0 00-3.712 0l-1.157 1.157 3.712 3.712 1.157-1.157a2.625 2.625 0 000-3.712zM19.513 8.199l-3.712-3.712-12.15 12.15a5.25 5.25 0 00-1.32 2.214l-.8 2.685a.75.75 0 00.933.933l2.685-.8a5.25 5.25 0 002.214-1.32L19.513 8.2z" />
      </svg>
      <span>Edit</span>
    </button>
  </div>
</div>
{#if isEditing}
  <CForm onCancel={toggleForm} idtoadd ={idfordetail}/>
{/if}
