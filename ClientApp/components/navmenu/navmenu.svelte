<script>
    import IndexHandler from '../../index.handler';
    import RouterLink from './routerlink.svelte';

    export let currentPath = '';

    IndexHandler.notify = routeData => {
        const path = routeData ? routeData.pathname : '';
        currentPath = '/' + path;
        // console.log('NavMenu : routeData', routeData, path, currentPath);
    };
</script>

<div class="top-row pl-4 navbar navbar-dark">
    <a class="navbar-brand" href="/">ASP.Net Svelte</a>
    <button class="navbar-toggler">
        <span class="navbar-toggler-icon"></span>
    </button>
</div>
<div class="collapse">
    <ul class="nav flex-column">
        <RouterLink className="nav-item px-3" to="/" location={currentPath}>
            <span class="oi oi-home" aria-hidden="true"></span> Home
        </RouterLink>
        <RouterLink className="nav-item px-3" to="/counter" location={currentPath}>
            <span class="oi oi-plus" aria-hidden="true"></span> Counter
        </RouterLink>
        <RouterLink className="nav-item px-3" to="/fetchdata" location={currentPath}>
            <span class="oi oi-list-rich" aria-hidden="true"></span> Fetch data
        </RouterLink>
    </ul>
</div>
