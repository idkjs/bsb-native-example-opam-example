bsb-native-example-opam
---

This is a quick demo project to showcase [bsb-native](https://github.com/bsansouci/bsb-native).

For publishing on opam see [opam_of_packagejson](https://github.com/bsansouci/opam_of_packagejson/) as a helper.


## Install
`npm i`

## Build bytecode
`npm run build`

To build other targets (like native or js) you can call bsb directly (or add a script) with the `-backend` flag, like `./node_nodules/.bin/bsb -backend native` or `./node_nodules/.bin/bsb -backend js`.

## Run
`./lib/bs/bytecode/index.byte`

## Switch

Must be on `opam switch4.02.3+buckle-master`. Run `opam switch create 4.02.3+buckle-master`

Then try adding following to `bsconfig.json`

```json
    "ocaml-dependencies": ["unix", "threads", "compiler-libs"],
    "ocamlfind-dependencies": ["lwt.unix", "lwt.ppx","cohttp", "lwt", "lwt.unix", "cohttp.lwt", "Yojson"],
```


Will have to run `opam install cohttp-lwt-unix cohttp-lwt lwt_ppx`. Note the dashes for the filenames which dont correspond to `cohttp.lwt` etc.

```sh
~/Downloads/bsb-native-example-opam-example graphql*
❯ opam install cohttp-lwt-unix cohttp-lwt
The following dependencies couldn't be met:
  - cohttp-lwt → ocaml >= 4.03.0
      base of this switch (use `--unlock-base' to force)

No solution found, exiting
```