<script>
	import Header from '$lib/header/Header.svelte';
	import '../app.scss';
	let logined = 1;
</script>

<Header />

<main>
	<slot />
</main>
{#if logined}
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
{/if}

<style lang="scss">
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
