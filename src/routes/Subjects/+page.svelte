<script></script>

<svelte:head>
	<title>Предметы</title>
	<meta name="description" content="Subjects" />
</svelte:head>
<main>
	<section class="subject-choice">
		<div class="subject-choice__container _container">
			<div class="subject-choice__title title title_dark">Выбери предмет:</div>
			<div class="subject-choice__row">
				<div class="subject-choice__col">
					<a href="/chapters.html" class="subject-choice__item" style="background: #75F491;"
						>Русский язык</a
					>
				</div>
				<div class="subject-choice__col">
					<a href="/chapters.html" class="subject-choice__item" style="background: #F98F62;"
						>Английский</a
					>
				</div>
				<div class="subject-choice__col">
					<a href="/chapters.html" class="subject-choice__item" style="background: #EBEE6D;"
						>География</a
					>
				</div>
			</div>
			<div class="subject-choice__row">
				<div class="subject-choice__col">
					<a href="/chapters.html" class="subject-choice__item" style="background: #4F79E4;"
						>Алгебра</a
					>
				</div>
				<div class="subject-choice__col">
					<a href="/chapters.html" class="subject-choice__item" style="background: #85D0FA;"
						>Геометрия</a
					>
				</div>
				<div class="subject-choice__col">
					<a href="/chapters.html" class="subject-choice__item" style="background: #B98FEE;"
						>Физика</a
					>
				</div>
			</div>
			<div class="subject-choice__row">
				<div class="subject-choice__col">
					<a href="/chapters.html" class="subject-choice__item" style="background: #FF537C;"
						>Литература</a
					>
				</div>
				<div class="subject-choice__col">
					<a href="/chapters.html" class="subject-choice__item" style="background: #68EAD2;"
						>Биология</a
					>
				</div>
				<div class="subject-choice__col">
					<a href="/chapters.html" class="subject-choice__item" style="background: #EF78F1;"
						>История</a
					>
				</div>
			</div>
		</div>
	</section>
</main>

<style lang="scss">
	.subject-choice {
		padding-top: 110px;

		&__title {
			margin-bottom: 60px;
			text-align: center;
		}

		&__row {
			display: flex;
			margin: -30px 0;
		}

		&__col {
			flex: 1 1 33.33%;
			padding: 35px 40px;
		}

		&__item {
			display: block;
			padding: 33px 0;
			width: 100%;
			text-align: center;
			font-size: 34px;
			color: white;
			border-radius: 34px;
		}
	}
</style>
