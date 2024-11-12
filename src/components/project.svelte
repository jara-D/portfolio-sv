<script>
	export let project;
</script>

<div
	class="project"
	style="
	--first-color:{project.color[0]};
	--second-color:{project.color[1]};
	--third-color:{project.color[2]};
	--fourth-color:{project.color[3]};
	--text-color:{project.color[4]};"
>
	<div class="text">
		<h2>{project.title}</h2>
		<p>{project.description}</p>
		<a href="projects/{project.slug}" class="button">See Project</a>
	</div>
	<div class="img">
		<div class="filter">
			<img src={project.image} alt="{project.title} image" />
		</div>
	</div>
</div>

<style>
	.project::before {
		content: '';
		width: 100%;
		height: 10px;
		position: absolute;
		background: linear-gradient(90deg, var(--first-color) 35%, var(--second-color) 35%);
		translate: 0 -9px;
	}
	.project {
		background-color: var(--third-color);
		display: grid;
		grid-template-columns: 1fr 1.86fr;
		padding-bottom: 20px;
		color: var(--text-color);
	}
	.text {
		padding-left: 10px;
	}
	.button {
		background-color: var(--first-color);
		color: var(--text-color);
		text-decoration: none;
		border: none;
		font-size: calc(0.9rem + 1vw);
		padding: 10px 20px;
		border-radius: 5px;
		cursor: pointer;
	}
	.img {
		display: flex;
		justify-content: center;
		align-items: center;
		padding-top: 20px;
		padding-bottom: 20px;
		position: relative;
	}
	.img img {
		border-radius: 10px;
		width: 100%;
		position: relative;
	}
	.img > .filter {
		background: radial-gradient(var(--second-color) 30%, rgba(0, 0, 0, 0) 70%);
		padding: 60px;
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	@media (min-width: 1500px) {
		.img img {
			width: 70%;
		}
	}

	@media (max-width: 900px) {
		.project {
			grid-template-columns: 1fr;
		}
		.img > .filter {
			width: 100%;
			background: none;
			padding: 0;
			display: flex;
			justify-content: center;
			align-items: center;
		}
		.img img {
			width: 90%;
			border-radius: 10px;
			background: linear-gradient(270deg, var(--fourth-color), var(--second-color) 50%);
			padding: 6px;
			margin: 0;
		}
	}
</style>
