<script>
</script>

<svelte:head>
	<title>Главная</title>
	<meta name="description" content="demo app" />
</svelte:head>

<section class="promo">
	<div class="promo__container _container">
		<div class="promo__title">Играй и обучайся одновременно!</div>
		<div class="promo__subtitle">Для школьников всех возрастов</div>
		<button class="promo__btn btn">Начать</button>
	</div>
</section>

<section id="about" class="about">
	<div class="about__container _container">
		<div class="about__title title">О нас</div>
		<div class="about__items">
			<div class="about-item">
				<div class="about-item__image">
					<div class="temp-image"></div>
				</div>
				<div class="about-item__title">Обучение в игровой форме</div>
				<div class="about-item__divider"></div>
				<div class="about-item__subtitle">Совмещай полезное с приятным</div>
			</div>
			<div class="about-item">
				<div class="about-item__image">
					<div class="temp-image"></div>
				</div>
				<div class="about-item__title">Большой банк заданий</div>
				<div class="about-item__divider"></div>
				<div class="about-item__subtitle">Узнавай что-то новое с каждым разом</div>
			</div>
			<div class="about-item">
				<div class="about-item__image">
					<div class="temp-image"></div>
				</div>
				<div class="about-item__title">Достижения за лучший результат</div>
				<div class="about-item__divider"></div>
				<div class="about-item__subtitle">Получай достижения и соревнуйся с другими учениками</div>
			</div>
		</div>
		<button class="about__btn btn">Узнать больше</button>
	</div>
</section>

<section class="subjects">
	<div class="subjects__container _container">
		<div class="wrapper subjects__wrapper">
			<div class="subjects__title title">Выбор предмета и темы</div>
			<div class="subjects__divider divider"></div>
			<div class="subjects__subtitle subtitle">Проходи задания по любой выбранной теме</div>
		</div>
		<div class="subjects__subjects">
			<div class="subjects__row">
				<div class="subjects__col"><div class="subjects__subject" style="background: #75F491;">Русский язык</div></div>
				<div class="subjects__col"><div class="subjects__subject" style="background: #F98F62;">Английский</div></div>
				<div class="subjects__col"></div>
			</div>
			<div class="subjects__row">
				<div class="subjects__col"><div class="subjects__subject" style="background: #4F79E4;">Алгебра</div></div>
				<div class="subjects__col"><div class="subjects__subject" style="background: #85D0FA;">Геометрия</div></div>
				<div class="subjects__col"><div class="subjects__subject" style="background: #B98FEE;">Физика</div></div>
			</div>
			<div class="subjects__row">
				<div class="subjects__col"><div class="subjects__subject" style="background: #FF537C;">Литература</div></div>
				<div class="subjects__col"><div class="subjects__subject" style="background: #68EAD2;">Биология</div></div>
				<div class="subjects__col"><div class="subjects__subject" style="background: #EF78F1;">История</div></div>
			</div>
		</div>
		<div class="subjects__curve"></div>
	</div>
</section>

<section id="helpers" class="helpers">
	<div class="helpers__container _container">
		<div class="helpers__body">
			<div class="wrapper helpers__wrapper">
				<div class="helpers__title title title_light">Твои помощники в учебе</div>
				<div class="helpers__divider divider divider_light"></div>
				<div class="helpers__subtitle subtitle subtitle_light">Оригинальный персонаж для каждого предмета, который будет направлять и помогать</div>
				<button class="btn helpers__btn">Посмотреть</button>
			</div>
		</div>
		<div class="helpers__image">
			<img src="images/helpers.png" alt="">
		</div>
	</div>
</section>
<section id="achievements" class="achievements">
	<div class="_container achievements__container">
		<div class="achievements__row">
			<div class="achievements__col">
				<div class="achievements__medals medals">
					<div class="medals__col">
						<div class="medals__item">
							<img src="images/medal01.svg" alt="">
						</div>
						<div class="medals__item">
							<img src="images/medal02.svg" alt="">
						</div>
						<div class="medals__item">
							<img src="images/medal03.svg" alt="">
						</div>
					</div>
					<div class="medals__col">
						<div class="medals__item">
							<img src="images/medal01.svg" alt="">
						</div>
						<div class="medals__item">
							<img src="images/medal02.svg" alt="">
						</div>
						<div class="medals__item">
							<img src="images/medal03.svg" alt="">
						</div>
					</div>
					<div class="medals__col">
						<div class="medals__item">
							<img src="images/medal01.svg" alt="">
						</div>
						<div class="medals__item">
							<img src="images/medal02.svg" alt="">
						</div>
						<div class="medals__item">
							<img src="images/medal03.svg" alt="">
						</div>
					</div>
				</div>
			</div>
			<div class="achievements__col">
				<div class="wrapper achievements__wrapper">
					<div class="achievements__title title">Получай достижения</div>
					<div class="achievements__divider divider"></div>
					<div class="achievements__subtitle subtitle">Пройди задания быстро и правильно и получи достижение</div>
				</div>
			</div>
			<div class="achievements__col">
				<div class="achievements__medals medals">
					<div class="medals__col">
						<div class="medals__item">
							<img src="images/medal01.svg" alt="">
						</div>
						<div class="medals__item">
							<img src="images/medal02.svg" alt="">
						</div>
						<div class="medals__item">
							<img src="images/medal03.svg" alt="">
						</div>
					</div>
					<div class="medals__col">
						<div class="medals__item">
							<img src="images/medal01.svg" alt="">
						</div>
						<div class="medals__item">
							<img src="images/medal02.svg" alt="">
						</div>
						<div class="medals__item">
							<img src="images/medal03.svg" alt="">
						</div>
					</div>
					<div class="medals__col">
						<div class="medals__item">
							<img src="images/medal01.svg" alt="">
						</div>
						<div class="medals__item">
							<img src="images/medal02.svg" alt="">
						</div>
						<div class="medals__item">
							<img src="images/medal03.svg" alt="">
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>

<style lang="scss">
.promo {
	background: url(images/promo-bg.svg) no-repeat 0 0 / cover;

	&__container {
		padding-top: 200px;
		padding-bottom: 150px;
		padding-left: 150px;
		padding-right: 300px;
	}

	&__title {
		font-size: 70px;
		font-weight: 700;
		color: white;
	}

	&__subtitle {
		margin-top: 15px;
		font-size: 40px;
		font-weight: 300;
		color: white;
	}

	&__btn {
		margin-top: 30px;
		margin-left: 20px;
		font-size: 40px;
		padding: 10px 50px;
		border-radius: 90px;
	}
}




.about{
	padding-top: 60px;
	padding-bottom: 100px;

	&__container{

		display: flex;
		flex-direction: column;
		align-items: center;
	}
	&__title{
		margin-bottom: 70px;
	}
	&__btn{
		margin-top: 40px;
	}
	&__items{
		display: flex;
	}
}
.about-item{
	width: 270px;
	display: flex;
	align-items: center;
	border-radius: 30px;
	flex-direction: column;
	padding: 40px 20px;
	box-shadow: 0 4px 10px rgba(black, .4);
	margin: 0 20px;

	&__image{
		width: 100px;
		height: 100px;
		margin-bottom: 30px;
	}
	&__title{
		color: black;
		font-size: 20px;
		text-align: center;
	}
	&__divider{
		width: 100%;
		height: 1px;
		background-color: black;
		margin: 15px 0;
	}
	&__subtitle{
		color: black;
		font-size: 18px;
		font-weight: 300;
		text-align: center;
	}
}






.subjects {

	&__row{
		display: flex;
		margin: -30px -50px;
	}
	&__col{
		flex: 1 1 33.3%;
		padding: 30px 50px;
	}
	&__wrapper{
		width: 34%;
		align-items: flex-end;
		margin-left: auto;
	}
	&__title{
		text-align: end;
	}
	&__subtitle {
		text-align: end;
	}

	&__subjects {
	}

	&__subject {
		background-color: #000;
		color: white;
		width: 100%;
		padding: 40px 0;
		text-align: center;
		font-size: 30px;
		border-radius: 10px;
		box-shadow: 0 3px 15px rgba(blue, .5);

		&:nth-child(1) {
			background-color: purple;
		}
	}

	background: url(images/curve01.svg) bottom / 100% auto no-repeat;
}






.helpers {
	padding-top: 150px;
	background: #aba9ff url(images/curve02.svg) bottom / 100% 100% no-repeat;
	&__container{
		display: flex;
	}
	&__body{
		flex: 1 1 55%;
	}
	&__image{
		flex: 1 1 45%;
		img{
			width: 100%;
			height: 100%;
			object-fit: contain;
		}
	}
	&__btn{
		margin-top: 60px;
		align-self: self-start;
	}
}





.achievements{
	&__row {
		display: flex;
		margin: 0 -20px;
	}
	&__col {
		flex: 1 1 33.33%;
		padding: 0 20px;
		&:nth-child(3) {
			.medals__col {
				&:nth-child(1) {
					order: 3
				}
				&:nth-child(2) {
					order: 2
				}
				&:nth-child(3) {
					order: 1
				}
			}
		}
	}
	&__title {
		text-align: center;
	}
	&__subtitle {
		text-align: center;
	}
	&__medals {

	}
}

.medals {
	display: flex;
	justify-content: space-between;
	&__col {
		display: flex;
		flex-direction: column;
		&:nth-child(1) {
			padding-top: 126px;
		}
		&:nth-child(3) {
			padding-top: 60px;
		}
	}
	&__item {
		width: 110px;
		height: 110px;
		img {
			width: 100%;
			height: 100%;
			object-fit: contain;
		}
		&:not(:last-child) {
			margin-bottom: 30px;
		}
	}
}
</style>
