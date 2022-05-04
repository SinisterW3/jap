html,
body
	min-height: 100%
	
body
	background: radial-gradient(ellipse at center, #ffc200 0%, #e0ad00 100%)

.player
	box-shadow: 0 2px 4px -4px rgba(0, 0, 0, .4), 0 50px 45px -20px rgba(0, 0, 0, .2)
	border-radius: 30px
	height: 400px
	margin: 50px auto
	overflow: hidden
	position: relative
	width: 400px
	
	&__meta
		box-sizing: border-box
		font-size: 24px
		padding: 50px 20px
		position: absolute
		text-align: center
		text-shadow: 0 1px 1px rgba(255, 255, 255, .4)
		top: 0
		width: 100%
		z-index: 1
	
	&__artist
		font-weight: 300
	
	&__bg
		background-position: bottom center
		background-size: cover
		height: 100%
		position: absolute
		width: 100%
	
		&:before,
		&:after
			content: ''
			display: block
			height: 100%
			position: absolute
			width: 100%
		
		&:after
			background: linear-gradient(to top, #000, #fff)
			opacity: .2
			mix-blend-mode: soft-light
	
	&__controls
		background-color: rgba(255, 255, 255, .2)
		bottom: 0
		box-shadow: inset 0 1px rgba(255, 255, 255, .3)
		height: 80px
		position: absolute
		width: 100%
		
		&:before,
		&:after
			content: ''
			height: 100%
			display: block
			pointer-events: none
			position: absolute
			width: 100%
	
		&:before
			box-shadow: 0 -5px 10px 0 rgba(0, 0, 0, .6)
			mix-blend-mode: soft-light

		// &:after
		// 	background-color: rgba(0, 0, 0, .1)
	
		&-bg
			background-position: bottom center
			background-size: cover
			height: 100%
			filter: blur(30px)
			overflow: hidden
			position: absolute
			width: 100%
			
			&:before
				background: linear-gradient(to top, #000, #fff)
				content: ''
				display: block
				height: 100%
				opacity: .08
				mix-blend-mode: soft-light
				position: absolute
				width: 100%
	
	&__play,
	&__prev,
	&__next
		background: rgba(255, 255, 255, .01)
		border-radius: 60px
		bottom: 0
		box-shadow: 0 -2px 4px 0 rgba(255, 255, 255, .1)
		cursor: pointer
		left: 0
		margin: auto
		position: absolute
		right: 0
		top: 0
		transition: background .15s linear
	
		.player__icon
			transition: transform .05s linear
	
		&:before,
		&:after
			border-radius: 60px
			content: ''
			display: block
			height: 100%
			position: absolute
			width: 100%
	
		&:before
			background: linear-gradient(to top, rgba(255, 255, 255, .1), rgba(255, 255, 255, .04))
			box-shadow: 0 -1px 1px 0 rgba(255, 255, 255, .6)
			mix-blend-mode: overlay
		
		&:after
			box-shadow: 0 5px 10px 0 rgba(0, 0, 0, .6)
			mix-blend-mode: soft-light
		
		&:hover
			background: radial-gradient(ellipse at center, rgba(12, 11, 23, .4) 0%, rgba(86, 76, 132, .1) 60%, rgba(255, 255, 255, .2) 100%)

			.player__icon
				transform: scale(.9)

	&__play
		height: 60px
		width: 60px
	
	&__prev,
	&__next
		height: 40px
		width: 40px

	&__prev
		right: 120px
	
	&__next
		left: 120px
	
	&__icon
		bottom: 0
		color: rgba(0, 0, 0, .8)
		cursor: pointer
		height: 1em
		left: 0
		margin: auto
		position: absolute
		right: 0
		top: 0
		width: 1.4em
		
		&:before
			text-shadow: 0 1px 1px rgba(255, 255, 255, .2)
		
		&-play
			font-size: 30px
			width: 1.2em
		
		&-prev,
		&-next
			width: 1.4em
	
	&__repeat
		left: .5em
		width: 1.4em

	&__shuffle
		right: .5em
		width: 2em
	
	&__repeat,
	&__shuffle
		bottom: 0
		color: #1A0C1D
		height: 1.2em
		font-size: 30px
		margin: auto
		position: absolute
		top: 0
	
	&__list
		height: 1.2em
		font-size: 20px
		left: 20px
		position: absolute
		top: 30px
		width: 1.4em
		z-index: 1

	&__volume
		height: 1.2em
		font-size: 26px
		right: 20px
		position: absolute
		top: 30px
		width: 1.4em
		z-index: 1
