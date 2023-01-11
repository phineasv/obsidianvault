- Integration of multiplayer online gaming and cloud gaming paradigms (Deng et. al., 2018)

- Remote rendering architecture  (Gao, et al., 2022)
	- game server
		- Same with [[Conventional Multiplayer Gaming|traditional gaming server]]
		- Executing game logics
			- maintain consitent game states among players
			- process login/out
			- storing players' info
	- Rendering server
		- "client" connected to game server to exchange game states
		- "servers", utilized to render game scenes, stream it to thin-client devices
		- Thin-clieent devics send user interaction inputs and displaying game scene

- Have same advantages and disadvantages as a typical [[Cloud Gaming]] service

- Edge computing is a good technique for supporting it. [[MEC]] 


![[Screen Shot 2022-12-07 at 3.23.07 PM.png]]
(Deng et al., 2018)