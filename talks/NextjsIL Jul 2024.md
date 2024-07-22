Communication as an implementation detail

Talk
* Generate next app with turbo
  ```bash
  pnpm dlx create-next-app@latest next-jul-conf
    ```
* show off server actions
	* server function that appends to a file (and maybe confetti)
	* form to use it
* explain the DX
* what if we wanted to do it with fetch instead
	* route to call it
	* client fetch in onSubmit
* why do we need to choose? (what about RPC\server events\socket\...)
	* What would we want (export const type = 'websocket')?
	* How would we support that 
		* prebuild tool
		* code gen
	* Make the simple change to use socket

Demo
