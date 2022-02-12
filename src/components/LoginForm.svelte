<script>
    import {
        Form,
        Input,
        FormGroup,
        CardText,
        Button
    } from 'sveltestrap';
</script>

<Form>
    <FormGroup floating label="email" class="mb-3">
        <Input type="email" placeholder="name@example.com"></Input>
    </FormGroup>
    <FormGroup floating label="Mot de passe" class="mb-3">
        <Input type="password" placeholder="Mot de passe"></Input>
    </FormGroup>

    <FormGroup class="mb-5">
        <Input id="c1" type="checkbox" label="Rester connecté"/>
    </FormGroup>
    <Button dark size="lg" class="w-100 text-uppercase" type="submit">Se connecter</Button>
    <CardText class="mt-3 text-muted text-center border-top pt-2">Pas encore inscrit ?</CardText>
    <Button outline dark size="lg" class="w-100 text-uppercase" type="submit">S'enregistrer</Button>
    <CardText class="mt-5 mb-3 text-muted text-center">&copy; 2017–2021</CardText>
</Form>


<style>
    
</style>