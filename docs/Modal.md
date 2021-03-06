# Modal

The Modal component encapsulates typically modal behaviour as opening and closing, it does this while ensuring only one Modal is open at all times. As always in Renderless-Svelte the actual implementation of the look and feel of the Modal, including potential backdrops is completely up to the user.

In order to work the Modal has to be defined in the markup _somewhere_, this can be easily done in places like _App.svelte_, or if using Sapper __layout.svelte_.  Since it shares resources accross the board, it could even be mounted as seperate component in the _index.js_ file.

## The opening function

The `open` function, exposed from the Modal takes as an argument a payload, it is this payload that will be send on to the Modal itself.

```js
import { openModal } from 'renderless-svelte'

openModal({ ... })
```

## The Modal component

The Modal component takes a slot that will be shown if a payload has been send to the Modal.  It exposes two fields:

- _payload_ will have the aforementioned payload
_ _close_ is a function that closes the Modal

```svelte
<script>
    import { Modal } from 'renderless-svelte'
</script>

<Modal let:payload let:close>
    <button on:click="{close}">Close</button>
    <span>{payload}</span>
</Modal>
```

## Examples

* [Plain modal](https://www.renderless-svelte.dev/components/modal/example-plain)
* [Component based](https://www.renderless-svelte.dev/components/modal/example-component)
* [Dynamic content](https://www.renderless-svelte.dev/components/modal/example-dynamic)
