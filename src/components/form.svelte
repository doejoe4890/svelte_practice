<script>
    import TextInput from './input_controls/textInput.svelte';
    import {fly, fade} from 'svelte/transition'

    let submitted = false;
    let isSuccessVisible = false;

    function handleSubmit(e){
        isSuccessVisible = true;
        setTimeout (function() {
            isSuccessVisible = false;
        }, 4000);
    }
</script>

{#if isSuccessVisible}
    <p class="error-alert" transition:fade={{duration:150}}>Data Uploaded Successfully</p>
{/if}

<div class="isolate bg-white px-6 py-24 sm:py-32 lg:px-8">
 
  <div class="mx-auto max-w-2xl text-center">
    <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Form Control</h2>
    <br />
  </div>

    <form id="surveyForm"  on:submit|preventDefault={handleSubmit} >
        <div class="grid grid-rows-3 grid-flow-col gap-4">
            <div class="row-span-3">
                <TextInput
                    name = {"First Name"}
                    label = {"First Name"}
                    placeholder = {"First Name"}
                    required = {true}
                />
            </div>
            <div class="row-span-3">
                <TextInput
                    name = {"Last Name"}
                    label = {"Last Name"}
                    placeholder = {"Last Name"}
                    required = {true}
                />
            </div>
        </div>
        <br />
        <TextInput
            name = {"Comments"}
            label = {"Comments"}
            placeholder = {"Comments"}
            textarea = {true}
            required = {false}
            rows = {"5"}
        />
        <br />
        <button 
            class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" 
            on:click={() => submitted = true}
        >
            Continue
        </button>
    </form>
</div>