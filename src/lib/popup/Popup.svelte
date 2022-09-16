<script>
	export let active = false;
	let close = () => active = false;
</script>

<form action="#" class:_active={active} class="popup">
	<div on:click={close} class="popup__bg" />
	<div class="popup__content">
		<slot />
		<button on:click={close}
		type="button" class="popup__close">&#10006</button>
	</div>
</form>

<style lang="scss">
	.popup {
	&._active {
		.popup__bg {
			visibility: visible;
			opacity: 1;
		}
		.popup__content {
			top: 50%;
			transform: translate(-50%, -50%) scale(1, 1);
			opacity: 1;
		}
	}
	&__bg {
		position: fixed;
		width: 100%;
		height: 100%;
		top: 0;
		left: 0;
		z-index: 210;
		background-color: rgba(black, 0.6);

		visibility: hidden;
		opacity: 0;

		transition-property: visibility, opacity;
		transition-duration: 0.3s;
		transition-timing-function: ease;
	}
	&__content {
		position: fixed;
		z-index: 220;
		left: 50%;
		width: 370px;
		min-height: 100px;
		border-radius: 26px;
		background-color: #fff;
		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 20px 34px;

		top: 0;
		opacity: 0;
		transform: translate(-50%, -50%) scale(0, 0);

		transition-property: top, transform, opacity;
		transition-duration: 0.3s;
		transition-timing-function: ease;
	}
	&__close {
		position: absolute;
		left: 16px;
		top: 10px;
		font-size: 20px;
		color: $pink;
		line-height: 1;
		background-color: transparent;
	}
	&__title {
		font-size: 36px;
		margin-bottom: 44px;
	}
	&__input {
		color: $additionalText;
		padding: 9px 14px;
		border: 1px solid $additionalText;
		width: 100%;
		font-size: 16px;
		border-radius: 8px;
		margin-bottom: 25px;
		font-weight: 300;
		&:last-child {
			margin-bottom: 50px;
		}
	}
	&__btn {
		font-size: 23px;
	}
	&__link {
		margin-top: 33px;
		font-size: 17px;
		color: $additionalText;
		font-weight: 300;

		&:hover {
			cursor: pointer;
		}
	}
}
</style>
