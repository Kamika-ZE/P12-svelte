<script>
    import {
        Card,
        CardBody,
        CardSubtitle,
        CardText,
        CardTitle,
        CardLink,
        Container,
        Icon



    } from 'sveltestrap';

</script>
    <Container fluid class="d-flex justify-content-center align-items-center">
        <Card>
            <CardBody>
                <CardSubtitle class="text-center">Continuer avec</CardSubtitle>
                <CardText class="text-center my-3 fs-2 fw-bold">
                    <CardLink class="text-decoration-none text-dark"><Icon class="fab fa-github"/></CardLink>
                    <CardLink class="text-decoration-none text-dark"><Icon class="fab fa-google"/></CardLink>
                    <CardLink class="text-decoration-none text-dark"><Icon class="fab fa-linkedin"/></CardLink>
                </CardText>
                <CardTitle class="text-center mb-4">
                    Ou utilisez votre email
                </CardTitle>
                <slot/>
            </CardBody>
        </Card>

    </Container>

<style>

</style>