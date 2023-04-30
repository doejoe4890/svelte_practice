<script>
    export let label;
    export let placeholder;
    export let name;
    export let required;
    export let textarea;
    export let rows;
    let value=""
    let errorMessage="";
    let hasError = false;
    $: errorColor = errorMessage !== "" ? '#c00' : '#000';

    const handleInput = (e) => {
        value = e.target.value;
        if (value === "" && required){
            errorMessage = name + " " + "is Required"
        }
        else {
            errorMessage = ""
        }
    }
</script>


<h4 style="color: {errorColor}">
    {label}
    {#if required}
    <span class="text-red-700">*</span>
    {/if}
</h4>

<div class="form-group">
    {#if !textarea}
        <input
            type="text"
            class="form-control"
            placeholder={placeholder}
            on:input={handleInput}
            required = {required}
        />
    {:else}
        <textarea
            class="form-control"
            placeholder={placeholder}
            on:input={handleInput}
            required = {required}
            rows = {rows}
        />
    {/if}

    {#if errorMessage !== ""}
        <p class="text-red-700">{errorMessage}</p>
    {/if}

</div>

