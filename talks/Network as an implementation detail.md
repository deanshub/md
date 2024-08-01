# Network as an implementation detail
NextjsIL July 2024

note:
- what's this about
- me

---

# Demo Time

note: 
- Create turbo app
- Cleanup the first page

---

# Server Actions
note:
- first action
- DX

---

# Fetch
note:
- Replace server action with POST request

---

# Let's talk about it
note:
- What if I would have have wanted to change 100 apis?
- What if I would want to change it to Websocket \\ RPC \\ WebRTC \\ gRPC \\ server-sent events?

---

# Let's help nextjs move forward
note:
- API - DevEx (export const, comment, directive)
	- go back to use function by import
- Implementation
	- prebuild - cli package
	- stupid implementation
	- 
- try it out

---

# Summary
- I took shortcuts
	- working on source code - replace with a Webpack(or Turbopack) plugin\loader
	- working with AST instead of strings
	- HOF for next.config
	- watcher for changes
	- support rest of next commands
- Other thoughts: Websocket -> generators \\ cbor -> json

---
# Thank you
- [Demo Repository](https://github.com/deanshub/naaid)  

[@Dean Shub](https://x.com/deanshub)

note:
- It works
- Make next great again - talk potential

%% 
Talk
* Generate next app with turbo
  ```bash
  pnpm dlx create-turbo@latest next-jul-conf --example with-tailwind
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
 %%