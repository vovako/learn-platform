<script>
</script>

<svelte:head>
	<title>Главная</title>
	<meta name="description" content="demo app" />
</svelte:head>
	
<section class="greeting">
	<div class="greeting__container _container">
		<div class="greeting__title title title_light">Привет, Name!</div>
		<div class="greeting__subtitle subtitle subtitle_light">Готов приступить к занятиям?</div>
		<a href="/subjects.html"><button class="greeting__btn btn">Вперёд</button></a>
	</div>
</section>
<style lang="scss">
.greeting{
	background: url(./../images/promo-bg.svg) no-repeat 0 0 / cover;
	padding-top: 150px;
	&__container {
		justify-content: center;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	&__title {
		font-size: 70px;
		font-weight: 700;

		margin-bottom: 26px;
	}

	&__subtitle {
		font-size: 50px;

		margin-bottom: 77px;
	}

	&__btn {
		font-size: 40px;
		padding: 10px 50px;
	}
}
</style>