### How to customize Parity UI ?

If you choose to update the UI, for instance making custom images for all your ethereum accounts, it can be done quite easily. The UI is mainly written in React/Redux, the necessary files to update can be found in `./js`.

`./js/src/views` contains the main views.
`./js/src/ui` contains reusable components.

To build from the `./js` source:
`cargo build --release --no-default-features --features ui`

This will attempt to build the UI from source while building the binary instead of using precompiled version.

Also there is UI development mode:

npm start in the UI repo
1. Run node with `--ui-no-validation`
2. That should reflect the UI changes immediately at http://localhost:3000

