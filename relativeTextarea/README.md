## Relative textarea height based on your value....

Demo : [Link](https://svelte.dev/repl/37f426fe4b844598afbea850af05fc0b?version=3.43.1)

<br>

```html
<script>
	function relativeTextarea(node) {
		node.addEventListener("input", (event) => {
			node.style.height = "4px";
			node.style.height = 4 + event.target.scrollHeight + "px";
		});

		return {
			destroy() {
				node.removeEventListener("input", (event) => {
					node.style.height = "4px";
					node.style.height = 4 + event.target.scrollHeight + "px";
				});
			},
		};
	}
</script>

<textarea use:relativeTextarea></textarea>

<style>
	textarea {
		width: 300px;
		height: 40px;
		border: none;
		resize: none;
		border-bottom: 2px solid #000;
	}

	textarea:focus {
		border: none;
	}
</style>
```
