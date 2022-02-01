<script>
    import {
      Input,
      FormGroup
    } from 'sveltestrap';

    export let beaconTypes;
    export let selectedType;

    const renameType = (beaconType)=>{
        if (beaconType === 'course') {
            return 'Parcours';
        } else if (beaconType === 'project') {
            return 'Projet';
        } else {
            return 'Ressource';
        }
    };
</script>

<FormGroup class="my-2 my-lg-0">
    <Input type="select" name="menu" id="menu" bind:value={selectedType}>
        <option disabled selected value="">Catégorie</option>
        <option value="all">Tout</option>
        {#each beaconTypes as beaconType}
            <option value ={beaconType}>{renameType(beaconType)}</option>
        {/each}
    </Input>
</FormGroup>

<style>

</style>