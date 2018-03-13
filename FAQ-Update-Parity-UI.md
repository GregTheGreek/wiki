### Custom UI

If you choose to update the UI, for instance making custom images for all your ethereum accounts, it can be done quite easily. The UI is mainly written in React/Redux, the necessary files to update can be found in `./js`.

`./js/src/views` contains the main views.
`./js/src/ui` contains reusable components.

**NOTE:** In some cases, dependent on the branch you forked from, local UI changes may not be reflected immediately. This occurs due to the root `cargo.toml` looking for the pre-compiled version of the UI. If you encounter this issue, the quickest way to updating your changes is to point the rust compiler to the local `js` directory. A quick way to achieve this would be to edit `./dapps/cargo.toml` and modifying `ui-precompiled` line to point to `no-precompiled-js` (Although adding a cusotm hook to point to the local changes would be advised):

```
ui-precompiled = ["parity-ui/no-precompiled-js"]
```

##### Under The Hood
In the root `cargo.toml`, the UI is pointed to `./dapss/cargo.toml` which looks for the `ui-precompiled` hook. This hook references another `cargo.toml` located at `./dapps/cargo.toml` that searches for either the precompiled UI or local UI. By triggering the `no-preompiled-js` hook, parity will search for the `./js` in your root directory in favor of the precompiled version.
