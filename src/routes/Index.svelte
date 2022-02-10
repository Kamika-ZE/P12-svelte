<script>
	import { onMount } from 'svelte';

	import {
		Container,
		Row,
		Col
	} from 'sveltestrap';

	import { beaconData } from '../beaconData';
	import MenuType from '../components/MenuType.svelte';
	import SearchBar from '../components/SearchBar.svelte';
	import MiniBeacon from '../components/MiniBeacon.svelte';
	import NoResults from '../components/NoResults.svelte';

	let beaconTypes = []; //charge beacon type from beaconData
	let selectedType= ''; //menu selection
	let filteredBeacons = [];
	let searchText = '';


	// second try
	// let filters = [selectedType, searchTerm];

	//charge all type onMount from beaconData
	const getTypes = () => {
		for (let beacon of beaconData) {
			if (!beaconTypes.includes(beacon.type)) {
				beaconTypes = [...beaconTypes, beacon.type]
			}
		}
		beaconTypes = beaconTypes.sort();
	}
	onMount(() => getTypes());

	$: if(selectedType || searchText) filterBeacons();
  	const filterBeacons = () => {	
	  	filteredBeacons = beaconData.filter(({type, title}) => 
			//selcted type + search
			selectedType && selectedType == type
			&& searchText && title.toLowerCase().includes(searchText)
			// all type + search
			|| selectedType && selectedType == 'all'
			&& searchText && title.toLowerCase().includes(searchText)
			// all type no search
			|| !searchText && selectedType && selectedType == 'all'
			// no type + search
			|| searchText && !selectedType && title.toLowerCase().includes(searchText)
			// selected type no search
			|| !searchText && selectedType && selectedType == type
			
		);
		  return filteredBeacons;
  	}
</script>

<Container class="menu py-5">
    <Row class="g-3">
      <Col sm="3">
        <MenuType {beaconTypes} bind:selectedType />
      </Col>
      <Col sm="9">
        <SearchBar bind:searchText on:input={filterBeacons} />
      </Col>
    </Row>
</Container>

<Container>
{#if searchText && filteredBeacons.length == 0}
	<NoResults/>
{:else if filteredBeacons.length > 0}
	<Row class="row-cols-1 row-cols-sm-2 row-cols-md-3 g-3">
		{#each filteredBeacons as { type, title, authorName, organizationName }}
			<MiniBeacon {type} {title} {authorName} {organizationName} />
		{/each}
	</Row>
{:else}
	<Row class="row-cols-1 row-cols-sm-2 row-cols-md-3 g-3">
	{#each beaconData as { type, title, authorName, organizationName }}
		<MiniBeacon {type} {title} {authorName} {organizationName} />
	{/each}
	</Row>
{/if}
</Container>

<style>

</style>