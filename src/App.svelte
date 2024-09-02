<script>
    import {Route, Router} from "svelte-routing";
    import MainView from "./view/MainView.svelte";
</script>

<Router>
    <Route path="/" component={MainView}/>
</Router>