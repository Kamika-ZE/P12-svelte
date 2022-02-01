<script>
    import {
        Col,
        Card,
        CardBody,
        CardFooter,
        CardHeader,
        CardSubtitle,
        CardTitle,
        Button,
        Icon
        
    } from 'sveltestrap';
    let userName = 'Kkprout';
    export let type;
    export let authorName;
    export let organizationName;
    export let title;
    const renameType = (type)=>{
        if (type === 'course') {
            return 'Parcours';
        } else if (type === 'project') {
            return 'Projet';
        } else {
            return 'Ressource';
        }
    };
</script>


<Col>
    <Card class="border-none shadow-sm">
        <CardHeader class="d-flex flex-wrap flex-sm-row justify-content-between align-items-center">
            <CardTitle class="my-2 mr-2">{renameType(type)}</CardTitle>
            {#if authorName === userName}
                <Button secondary on:click>
                    <Icon class="far fa-edit" />
                </Button>
            {:else}
            <Button color="dark" on:click>Enregistrer</Button>  
            {/if}
        </CardHeader>
        <CardBody class="text-dark">
            <CardSubtitle class="text-uppercase text-muted mb-2">
                {organizationName}
            </CardSubtitle>
            <CardTitle>{title}</CardTitle>
        </CardBody>
        <CardFooter class="text-center">
            <Button outline color="dark" on:click>Voir</Button>  
        </CardFooter>
    </Card>
</Col>



<style>

</style>