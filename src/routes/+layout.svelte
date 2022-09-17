<script>
	import { page } from '$app/stores';
	import '../app.scss';
	import { onMount } from 'svelte';

	//header
	let menu = false;
	let menuClose = () => menu = false;

	import Popup from '$lib/popup/Popup.svelte';
	let regPopup, loginPopup = false;
	
	//вход в аккаунт
	let logined = false;
	onMount( () => {
		sessionStorage.setItem('logined', false);
		logined = sessionStorage.getItem('logined') == 'true';
	});
</script>

<header class="header">
	<div class="header__container _container">
		<button on:click={() => (menu = true)} class="header__menu-btn icon-menu">
			<span />
			<span />
			<span />
		</button>

		<div class="header__logo">
			<div class="logo">Логотип</div>
		</div>

		<div class:_inactive={!logined} class="header__profile profile">
			<div class="profile__body">
				<div class="profile__name">Name Name</div>
				<div class="profile__label">Личный кабинет</div>
			</div>
			<a class:active={$page.url.pathname === '/account'} href="/account" class="profile__avatar">
				<img src="./images/profile-icon.svg" alt="" />
			</a>
		</div>
	</div>

	<div class:_active={menu} class="menu-sidebar">
		<div on:click={menuClose} class="menu-sidebar__bg" />
		<div class="menu-sidebar__content">
			<button on:click={menuClose} class="menu-sidebar__close popup__close">&#10006</button>
			<ul class:_inactive={!logined} class="menu-sidebar__list">
				<li
					on:click={menuClose}
					class:active={$page.url.pathname === '/'}
					class="menu-sidebar__item"
				>
					<a href="/">Главная</a>
				</li>
				<li on:click={menuClose} class:active={$page.url.pathname === '/persons'} class="menu-sidebar__item">
					<a href="/persons">Персонажи</a>
				</li>
				<li on:click={menuClose} class:active={$page.url.pathname === '/subjects'} class="menu-sidebar__item">
					<a href="/subjects">Предметы</a>
				</li> 
				<li on:click={menuClose} class:active={$page.url.pathname === '/account'} class="menu-sidebar__item">
					<a href="/account">Кабинет</a>
				</li>
			</ul>
			{#if (!logined)}
				<button on:click={() => loginPopup = true} class="btn btn_dark menu-sidebar__btn">Войти</button>
				<button on:click={() => regPopup = true} class="btn menu-sidebar__btn">Регистрация</button>
			{/if}
		</div>
	</div>
</header> 

<main class:fullscreen={logined}>
	{#if (logined)}
		<slot></slot>
	{:else}
		<section class="promo">
			<div class="promo__container _container">
				<div class="promo__title">Играй и обучайся одновременно!</div>
				<div class="promo__subtitle">Для школьников всех возрастов</div>
				<button on:click={()=>{loginPopup = true}} class="promo__btn btn">Начать</button>
			</div>
		</section>
		<section id="about" class="about">
			<div class="about__container _container">
				<div class="about__title title">О нас</div>
				<div class="about__items">
					<div class="about-item">
						<div class="about-item__image">
							<div class="temp-image" />
						</div>
						<div class="about-item__title">Обучение в игровой форме</div>
						<div class="about-item__divider" />
						<div class="about-item__subtitle">Совмещай полезное с приятным</div>
					</div>
					<div class="about-item">
						<div class="about-item__image">
							<div class="temp-image" />
						</div>
						<div class="about-item__title">Большой банк заданий</div>
						<div class="about-item__divider" />
						<div class="about-item__subtitle">Узнавай что-то новое с каждым разом</div>
					</div>
					<div class="about-item">
						<div class="about-item__image">
							<div class="temp-image" />
						</div>
						<div class="about-item__title">Достижения за лучший результат</div>
						<div class="about-item__divider" />
						<div class="about-item__subtitle">
							Получай достижения и соревнуйся с другими учениками
						</div>
					</div>
				</div>
				<button class="about__btn btn">Узнать больше</button>
			</div>
		</section>

	<section class="subjects">
		<div class="subjects__container _container">
			<div class="wrapper subjects__wrapper">
				<div class="subjects__title title">Выбор предмета и темы</div>
				<div class="subjects__divider divider" />
				<div class="subjects__subtitle subtitle">Проходи задания по любой выбранной теме</div>
			</div>
			<div class="subjects__subjects">
				<div class="subjects__row">
					<div class="subjects__col">
						<div class="subjects__subject" style="background: #75F491;">Русский язык</div>
					</div>
					<div class="subjects__col">
						<div class="subjects__subject" style="background: #F98F62;">Английский</div>
					</div>
					<div class="subjects__col" />
				</div>
				<div class="subjects__row">
					<div class="subjects__col">
						<div class="subjects__subject" style="background: #4F79E4;">Алгебра</div>
					</div>
					<div class="subjects__col">
						<div class="subjects__subject" style="background: #85D0FA;">Геометрия</div>
					</div>
					<div class="subjects__col">
						<div class="subjects__subject" style="background: #B98FEE;">Физика</div>
					</div>
				</div>
				<div class="subjects__row">
					<div class="subjects__col">
						<div class="subjects__subject" style="background: #FF537C;">Литература</div>
					</div>
					<div class="subjects__col">
						<div class="subjects__subject" style="background: #68EAD2;">Биология</div>
					</div>
					<div class="subjects__col">
						<div class="subjects__subject" style="background: #EF78F1;">История</div>
					</div>
				</div>
			</div>
			<div class="subjects__curve" />
		</div>
	</section>

	<section id="helpers" class="helpers">
		<div class="helpers__container _container">
			<div class="helpers__body">
				<div class="wrapper helpers__wrapper">
					<div class="helpers__title title title_light">Твои помощники в учебе</div>
					<div class="helpers__divider divider divider_light" />
					<div class="helpers__subtitle subtitle subtitle_light">
						Оригинальный персонаж для каждого предмета, который будет направлять и помогать
					</div>
					<button class="btn helpers__btn">Посмотреть</button>
				</div>
			</div>
			<div class="helpers__image">
				<img src="images/helpers.png" alt="" />
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
								<img src="images/medal01.svg" alt="" />
							</div>
							<div class="medals__item">
								<img src="images/medal02.svg" alt="" />
							</div>
							<div class="medals__item">
								<img src="images/medal03.svg" alt="" />
							</div>
						</div>
						<div class="medals__col">
							<div class="medals__item">
								<img src="images/medal01.svg" alt="" />
							</div>
							<div class="medals__item">
								<img src="images/medal02.svg" alt="" />
							</div>
							<div class="medals__item">
								<img src="images/medal03.svg" alt="" />
							</div>
						</div>
						<div class="medals__col">
							<div class="medals__item">
								<img src="images/medal01.svg" alt="" />
							</div>
							<div class="medals__item">
								<img src="images/medal02.svg" alt="" />
							</div>
							<div class="medals__item">
								<img src="images/medal03.svg" alt="" />
							</div>
						</div>
					</div>
				</div>
				<div class="achievements__col">
					<div class="wrapper achievements__wrapper">
						<div class="achievements__title title">Получай достижения</div>
						<div class="achievements__divider divider" />
						<div class="achievements__subtitle subtitle">
							Пройди задания быстро и правильно и получи достижение
						</div>
					</div>
				</div>
				<div class="achievements__col">
					<div class="achievements__medals medals">
						<div class="medals__col">
							<div class="medals__item">
								<img src="images/medal01.svg" alt="" />
							</div>
							<div class="medals__item">
								<img src="images/medal02.svg" alt="" />
							</div>
							<div class="medals__item">
								<img src="images/medal03.svg" alt="" />
							</div>
						</div>
						<div class="medals__col">
							<div class="medals__item">
								<img src="images/medal01.svg" alt="" />
							</div>
							<div class="medals__item">
								<img src="images/medal02.svg" alt="" />
							</div>
							<div class="medals__item">
								<img src="images/medal03.svg" alt="" />
							</div>
						</div>
						<div class="medals__col">
							<div class="medals__item">
								<img src="images/medal01.svg" alt="" />
							</div>
							<div class="medals__item">
								<img src="images/medal02.svg" alt="" />
							</div>
							<div class="medals__item">
								<img src="images/medal03.svg" alt="" />
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>
	{/if}
</main>
{#if !logined}
	<footer class="footer">
		<div class="footer__container _container">
			<div class="footer__row">
				<div class="footer__col">
					<div class="footer__logo" />
					<div class="logo">Логотип</div>
					<div class="footer__description">
						Lorem ipsum dolor sit amet consectetur adipisicing elit. A incidunt dolore numquam
						debitis saepe culpa dolor sunt laboriosam temporibus adipisci.
					</div>
				</div>
				<div class="footer__col">
					<div class="footer__title">Меню</div>
					<ul class="footer__menu">
						<li class="footer__menu-item">
							<a href="#about">О нас</a>
						</li>
						<li class="footer__menu-item">
							<a href="#helpers">Персонажи</a>
						</li>
						<li class="footer__menu-item">
							<a href="#achievements">Достижения</a>
						</li>
						<li class="footer__menu-item">
							<a href="#">Рейтинг</a>
						</li>
					</ul>
				</div>
				<div class="footer__col">
					<div class="footer__title">Контакты</div>
					<div class="footer__contacts">
						<div class="footer__contacts-item">aaaaa@gmail.com</div>
						<div class="footer__contacts-item">+79510389065</div>
					</div>
				</div>
				<div class="footer__col">
					<div class="footer__title">Ссылки</div>
					<div class="footer__social">
						<a href="#" class="footer__social-item">
							<img src="./images/vk.svg" alt="" />
						</a>
						<a href="#" class="footer__social-item">
							<img src="./images/telegram.svg" alt="" />
						</a>
					</div>
				</div>
			</div>
		</div>
		<div id="footer-arrow" class="footer__arrow">
			<img src="./images/arrow-top.svg" alt="" />
		</div>
	</footer>
	<Popup bind:active={regPopup}>
		<div class="popup__title">Регистрация</div>
		<input class="popup__input" type="text" placeholder="Имя">
		<input class="popup__input" type="text" placeholder="Фамилия">
		<input class="popup__input" type="text" placeholder="Класс">
		<input class="popup__input" type="email" placeholder="Email">
		<input class="popup__input" type="password" placeholder="Пароль">
		<input class="popup__input" type="password" placeholder="Повторите пароль">
		<button class="btn popup__btn">Зарегистрироваться</button>
	</Popup>
	<Popup bind:active={loginPopup}>
		<div class="popup__title">Вход</div>
		<input class="popup__input" type="text" placeholder="Логин">
		<input class="popup__input" type="password" placeholder="Пароль">
		<button on:click={() => {logined = true; loginPopup = false; menuClose}} class="btn popup__btn">Войти</button>
		<div on:click={() => { loginPopup = false; regPopup = true;}} id="no-account-btn" class="popup__link">Нет аккаунта?</div>
	</Popup>
{/if}

<style lang="scss">
	.header {
		width: 100%;
		background-color: #fff;
		box-shadow: 0 4px 10px rgba(darkBlue, 0.35);

		&__container {
			padding: 8px 0; 
			display: flex; 
			justify-content: space-between;
			align-items: center;
		}

		&__logo {
			flex-grow: 1;
		}

		&__menu-btn {
			margin-right: 40px;
		}

		&__btn {
			font-size: 24px;
			padding: 4px 17px;
		}
	}

	.menu-sidebar {
		&._active {
			.menu-sidebar__content {
				transform: translateX(0%);
			}

			.menu-sidebar__bg {
				opacity: 1;
				visibility: visible;
			}
		}

		&__bg {
			position: absolute;
			top: 0;
			left: 0;
			bottom: 0;
			z-index: 110;
			width: 100vw;
			height: 100vh;
			background-color: rgba(black, 0.4);

			opacity: 0;
			visibility: hidden;

			transition-property: visibility, opacity;
			transition-duration: 0.2s;
			transition-timing-function: ease;
		}

		&__content {
			position: absolute;
			top: 0;
			left: 0;
			bottom: 0;
			z-index: 120;
			background-color: white;
			width: 300px;
			height: 100vh;
			display: flex;
			flex-direction: column;
			justify-content: flex-end;
			padding: 75px 35px 45px;
			border-top-right-radius: 40px;
			border-bottom-right-radius: 40px;

			transform: translateX(-100%);
			transition: transform 0.3s ease;
		}

		&__list {
			flex: 1 1 auto;
			padding-left: 30px;
		}

		&__item {
			text-align: right;

			a {
				font-family: 'Futura PT Light';
				font-size: 35px;
			}

			&::after {
				content: '';
				display: block;
				width: 100%;
				height: 1px;
				background-color: #000;
				margin-top: 10px;
				margin-bottom: 3px;
			}
		}

		&__close {
			position: absolute;
			top: 15px;
			left: 15px;
			line-height: 1;
			background-color: transparent;
			font-size: 30px;
			color: pink;
		}

		&__btn {
			font-size: 26px;
			padding: 10px 0;

			&:not(:last-child) {
				margin-bottom: 14px;
			}
		}
	}

	.logo {
		background-color: gray;
		display: inline-block;
		color: white;
		padding: 10px 30px;
	}

	.profile {
		display: flex;
		align-items: center;

		&__login {
			button {
				&:first-child {
					margin-right: 8px;
				}
			}
		}

		&__body {
			display: flex;
			flex-direction: column;
			align-items: flex-end;
			justify-content: center;

			margin-right: 17px;
		}

		&__name {
			font-size: 18px;
			color: black;
		}

		&__label {
			font-size: 16px;
			font-weight: 300;
			color: black;

			margin-top: 2px;
		}

		&__avatar {
			width: 50px;
			height: 50px;
			border-radius: 50%;
			overflow: hidden;

			img {
				object-fit: cover;
				width: 100%;
				height: 100%;
			}
		}
	}

	.icon-menu {
		height: 30px;
		width: 40px;
		z-index: 5;
		position: relative;
		background-color: transparent;

		span {
			pointer-events: none;
			position: absolute;
			top: calc(50% - 3px);
			left: 0px;
			width: 100%;
			height: 6px;
			background-color: pink;
			border-radius: 6px;

			&:first-child {
				top: 0px;
			}

			&:last-child {
				top: auto;
				bottom: 0px;
			}
		}
	}
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

	.about {
		padding-top: 60px;
		padding-bottom: 100px;

		&__container {
			display: flex;
			flex-direction: column;
			align-items: center;
		}
		&__title {
			margin-bottom: 70px;
		}
		&__btn {
			margin-top: 40px;
		}
		&__items {
			display: flex;
		}
	}
	.about-item {
		width: 270px;
		display: flex;
		align-items: center;
		border-radius: 30px;
		flex-direction: column;
		padding: 40px 20px;
		box-shadow: 0 4px 10px rgba(black, 0.4);
		margin: 0 20px;

		&__image {
			width: 100px;
			height: 100px;
			margin-bottom: 30px;
		}
		&__title {
			color: black;
			font-size: 20px;
			text-align: center;
		}
		&__divider {
			width: 100%;
			height: 1px;
			background-color: black;
			margin: 15px 0;
		}
		&__subtitle {
			color: black;
			font-size: 18px;
			font-weight: 300;
			text-align: center;
		}
	}

	.subjects {
		&__row {
			display: flex;
			margin: -30px -50px;
		}
		&__col {
			flex: 1 1 33.3%;
			padding: 30px 50px;
		}
		&__wrapper {
			width: 34%;
			align-items: flex-end;
			margin-left: auto;
		}
		&__title {
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
			box-shadow: 0 3px 15px rgba(blue, 0.5);

			&:nth-child(1) {
				background-color: purple;
			}
		}

		background: url(images/curve01.svg) bottom / 100% auto no-repeat;
	}

	.helpers {
		padding-top: 150px;
		background: #aba9ff url(images/curve02.svg) bottom / 100% 100% no-repeat;
		&__container {
			display: flex;
		}
		&__body {
			flex: 1 1 55%;
		}
		&__image {
			flex: 1 1 45%;
			img {
				width: 100%;
				height: 100%;
				object-fit: contain;
			}
		}
		&__btn {
			margin-top: 60px;
			align-self: self-start;
		}
	}

	.achievements {
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
						order: 3;
					}
					&:nth-child(2) {
						order: 2;
					}
					&:nth-child(3) {
						order: 1;
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
	.footer {
		background: linear-gradient(164deg, #fd96ab -13%, #aba9ff 22% 59%, #fafc99 138%);
		font-size: 18px;
		color: white;
		position: relative;

		&__container {
			padding-top: 20px;
			padding-bottom: 60px;
			padding-right: 300px;
		}

		&__row {
			display: flex;
			margin: 0 -40px;
		}

		&__col {
			flex: 1 1 25%;
			padding: 0 40px;
		}

		&__description {
			margin-top: 10px;
			font-size: 15px;
		}

		&__title {
			font-size: 20px;
			margin-bottom: 10px;
		}

		&__menu {
			&-item {
				&:not(:last-child) {
					margin-bottom: 7px;
				}

				a {
					color: white;

					&:hover {
						color: yellow;
					}
				}
			}
		}

		&__contacts {
			&-item {
				&:not(:last-child) {
					margin-bottom: 7px;
				}
			}
		}

		&__social {
			display: flex;

			&-item {
				width: 40px;
				height: 40px;
				margin-right: 10px;
			}
		}
		&__arrow {
			position: absolute;
			top: 20px;
			right: 20px;
			width: 70px;
			height: 70px;
			cursor: pointer;
		}
	}
</style>
