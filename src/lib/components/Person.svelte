<script>
    export let name = '';
    export let img = '';
    export let href = '';
</script>

<div class="col-6 col-md-4 col-lg-3 d-flex align-items-center flex-column mb-2">
    <img src={img} class="img-fluid" alt="">
    <a {href}>
        <span class="font-xsmall mt-1">{name}</span>
    </a>
</div>