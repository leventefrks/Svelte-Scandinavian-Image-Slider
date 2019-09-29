<script>
	export let nav;
	export let title;
	export let content;
	export let contentSubText = "Are you ready to check it out?";
</script>

<style>
	.info {
	  position: relative;
	  display: flex;
	  flex-direction: column;
	  width: 35%;
	  height: 100%;
	  padding: 1rem 2rem 0;
	  background: #fff;
	}

	.nav-list {
	  display: flex;
	  justify-content: flex-end;
	  list-style-type: none;
	  text-transform: uppercase;
	}

	.nav-item {
	  margin-right: 1rem;
	  font-size: 0.9rem;
	}

	.nav-item-link {
	  color: #ccc;
	  text-decoration: none;
	  transition: color 0.2s ease-in;
	}

	.nav-item-link:hover {
	  color: #333;
	}

	article {
	  display: flex;
	  align-self: center;
	  justify-content: center;
	  flex-direction: column;
	}

	h1 {
	  position: relative;
	  font-size: 2.2rem;
	}

	h1:after {
	  position: absolute;
	  top: 100%;
	  left: 0;
	  width: 3.5rem;
	  content: " ";
	  padding-bottom: 1rem;
	  border-bottom: solid 4px rgb(227, 213, 213);
	}

	.content {
	  height: 10.5rem;
	  margin-bottom: 2rem;
	  color: #333;
	  font-size: 0.9rem;
	  line-height: 1.5rem;
	}

	span {
	  font-size: 0.9rem;
	}
</style>

<section class="info">
	<nav>
		<ul class="nav-list">
			{#each nav as navItem}
				<li class="nav-item">
					<a href="#" class="nav-item-link">{navItem}</a>
				</li>
			{/each}
		</ul>
	</nav>

	<article>
		<h1>{title}</h1>
		<p class="content">{content}</p>
		<span>{contentSubText}</span>
	</article>
</section>

