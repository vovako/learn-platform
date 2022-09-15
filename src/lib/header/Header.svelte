<script>
	import Popup from '../popup/Popup.svelte';
	import logo from './logo.png';
	import { page } from '$app/stores';
	let menu = false;
	let regPopup = false;
	let loginPopup = false;
	console.log('reg '+ regPopup);
</script>

<Popup id="reg-popup" active={regPopup}>
	<div class="popup__title">Регистрация</div>
	<input class="popup__input" type="text" placeholder="Имя">
	<input class="popup__input" type="text" placeholder="Фамилия">
	<input class="popup__input" type="text" placeholder="Класс">
	<input class="popup__input" type="email" placeholder="Email">
	<input class="popup__input" type="password" placeholder="Пароль">
	<input class="popup__input" type="password" placeholder="Повторите пароль">
	<button class="btn popup__btn" type="submit">Зарегистрироваться</button>
</Popup>
<Popup id="login-popup" active={loginPopup}>
	<div class="popup__title">Вход</div>
	<input class="popup__input" type="text" placeholder="Логин">
	<input class="popup__input" type="password" placeholder="Пароль">
	<button class="btn popup__btn" type="submit">Войти</button>
	<div id="no-account-btn" class="popup__link">Нет аккаунта?</div>
</Popup>

<header class="header">
	<div class="header__container _container">
		<button
			on:click={() => (menu = true)}
			type="button"
			data-popup-id="menu-sidebar"
			class="header__menu-btn icon-menu"
		>
			<span />
			<span />
			<span />
		</button>

		<div class="header__logo">
			<div class="logo">Логотип</div>
		</div>

		<div class="header__profile profile">
			<div class="profile__body">
				<div class="profile__name">Name Name</div>
				<div class="profile__label">Личный кабинет</div>
			</div>
			<a
				class:active={$page.url.pathname === '/account'}
				href="/account"
				class="profile__avatar _ibg"
			>
				<img src="./images/profile-icon.svg" alt="" />
			</a>
		</div>
	</div>

	<div class:_active={menu} class="menu-sidebar">
		<div on:click={() => (menu = false)} class="menu-sidebar__bg" />
		<div class="menu-sidebar__content">
			<button on:click={() => (menu = false)} class="menu-sidebar__close popup__close"
				>&#10006</button
			>
			<ul class="menu-sidebar__list">
				<li
					on:click={() => (menu = false)}
					class:active={$page.url.pathname === '/'}
					class="menu-sidebar__item"
				>
					<a href="/">Главная</a>
				</li>
				<li class:active={$page.url.pathname === '/persons'} class="menu-sidebar__item">
					<a href="/persons">Персонажи</a>
				</li>
				<li class:active={$page.url.pathname === '/subjects'} class="menu-sidebar__item">
					<a href="/subjects">Предметы</a>
				</li>
				<li class:active={$page.url.pathname === '/account'} class="menu-sidebar__item">
					<a href="/account">Кабинет</a>
				</li>
			</ul>
			<button on:click={() => (loginPopup = true)} data-popup-id="login-popup" class="btn btn_dark menu-sidebar__btn">Войти</button>
			<button on:click={() => (regPopup = true)} data-popup-id="reg-popup" class="btn menu-sidebar__btn">Регистрация</button>
		</div>
	</div>
</header>


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
</style>
