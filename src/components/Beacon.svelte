<script>
    import {
        Container,
        Row,
        Col,
        Card,
        CardBody,
        CardFooter,
        CardHeader,
        CardSubtitle,
        CardText,
        CardTitle,
        CardLink,
        Button,
        Image,
        Icon,
        ListGroup,
        ListGroupItem
        
    } from 'sveltestrap';

    let userName = 'Kkprout';
    let beaconId = '1';
    let beaconType = 'Type';
    let beaconTitle = 'Titre';
    let beaconOrganizationName = 'Organisation';
    let beaconOrganizationLink = 'https://www.organization.com';
    let beaconAuthorPicture = "";
    let beaconAuthorName = 'Kkprout';
    let beaconAuthorComment =  'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Asperiores itaque deleniti culpa veniam molestias. Tempora ipsa doloribus officia quibusdam delectus.';
    let beaconAssociates = [
        {id: '1', pTitle: 'Projet 1 - Concevez un cv avec HTML et CSS'},
        {id: '2', pTitle: 'Projet 2 - Créez la documentation fonctionnelle du projet'},
        {id: '3', pTitle: 'Projet 3 - Implémentez votre première API'},
        {id: '4', pTitle: 'Projet 4 - Tester ? Pourquoi faire ?'}
    ];



</script>

<Container class="py-5">
    <Row>
        <Col>
            <Card class="border-none shadow-sm">
                <CardHeader class="d-flex flex-wrap flex-sm-row justify-content-between align-items-center">
                    <CardTitle class="mb-0">{beaconType}</CardTitle>
                    {#if userName === beaconAuthorName}
                        <Button secondary on:click>
                            <Icon class="far fa-edit" />
                        </Button>
                    {:else}
                    <Button color="dark" on:click>Enregistrer</Button>  
                    {/if}
                </CardHeader>
                <CardBody class="text-dark">
                    <Row>
                        <Col class="">                           
                            <CardTitle class="my-4 text-break">
                                {beaconTitle}
                            </CardTitle>
                            <ListGroup flush class="mt-3">
                                <ListGroupItem class="px-0">
                                    <CardSubtitle class="text-break">
                                        Organisme de formation :
                                        <span class="text-muted text-uppercase">{beaconOrganizationName}</span>
                                    </CardSubtitle>    
                                </ListGroupItem>
                                <ListGroupItem class="px-0">
                                    <CardSubtitle class="">
                                        lien du parcours :
                                        <CardLink href="{beaconOrganizationLink}">
                                            {beaconOrganizationLink}
                                        </CardLink>
                                    </CardSubtitle> 
                                </ListGroupItem>
                            </ListGroup>
                        </Col>
                        <Col class="">
                            <CardText class="my-4">
                                <span>Balise créé par :&nbsp;</span>
                                {#if beaconAuthorPicture} 
                                    <Image src={beaconAuthorPicture} alt="author picture" class="img-fluid rounded-circle" width="40" height="40" />
                                {:else}
                                    <Icon class="fas fa-user-circle fa-2x"/>
                                {/if}
                                <span>{beaconAuthorName}</span>
                            </CardText>
                            <CardSubtitle>Commentaire de l'auteur :</CardSubtitle>
                            <CardText class="mt-2">
                                {beaconAuthorComment}
                            </CardText>
                        </Col>
                    </Row>
                </CardBody>
                <CardFooter class="text-center">
                    <ListGroup>
                        <ListGroupItem tag="button" action color="dark">
                            <Icon class="far fa-plus-square"/>&nbsp;Ajouter un projet
                        </ListGroupItem>
                        {#each beaconAssociates as associate}
                            <ListGroupItem class="my-2" tag="button" action>
                                <div class="d-flex w-100 justify-content-between">
                                    <CardTitle class="">{associate.pTitle}</CardTitle>
                                </div>
                            </ListGroupItem>
                        {/each}
                    </ListGroup>
                </CardFooter>
            </Card>
        </Col>
    </Row>
</Container>


<style>

</style>