<script>

    let ocs = [
        { id: 1, name: 'Gilbert' },
        { id: 2, name: 'Jerald' },
        { id: 3, name: 'Jacques'}
    ];

    let selected;

</script>


<div>

    <select bind:value={selected}>
        {#each ocs as oc}
            <option name={oc}>
                {oc.name}
            </option>
        {/each}
    </select>

</div>


<style>

</style>