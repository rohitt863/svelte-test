<script>
  import { Router, Link, Route } from "svelte-routing";
  import Button from "./Button.svelte";
  import Heading from "./Heading.svelte";
  let count = 0;
  let color = "#000000";
  export let url = "";

  const colors = ["#00ff00", "#ff0000", "#0000ff"];

  let handleClick = () => {
    count++;
    color = colors[Math.floor(Math.random() * 3)];
  };
</script>

<Router {url}>
  <header>
    <h1>History</h1>

    <nav>
      <Link to="/">Home</Link>
      <Link to="about">About</Link>
      <Link to="profile">Profile</Link>
    </nav>
  </header>

  <main>
    <Route path="about">
      <Button {color} {handleClick} />
    </Route>
    <Route path="login">
      <div>test</div>
    </Route>

    <Route path="/">
      <Heading {count} />
    </Route>
  </main>
</Router>
