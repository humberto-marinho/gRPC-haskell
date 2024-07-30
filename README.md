Attribution
-----------

This library is a fork of https://github.com/aloiscochard/grpc-haskell that we
have extended and released under the same [`LICENSE`](./LICENSE)

Installation
------------

**The current version of this library requires gRPC version 1.45.0. Newer versions may work but have not been tested.**

Usage
-----

There is a tutorial [here](examples/tutorial/TUTORIAL.md)

Building and testing
--------------------

`nix-build release.nix -A grpc-haskell` will build and test the whole thing and
put the completed package into the nix store. `nix-shell` can be used to give
you a development environment where you can use `cabal` for development and
testing:

```bash
$ nix-shell
[nix-shell]$ cabal configure --enable-tests && cabal build && cabal test
```

Using the Library
-----------------

You must compile with `-threaded`, because we rely on being able to execute
Haskell while blocking on foreign calls to the gRPC library. If not using code
generation, the recommended place to start is in the
`Network.GRPC.HighLevel.Server.Unregistered` module, where `serverLoop` provides
a handler loop.


Após dar git clone, executar na sequencia:
-----------------
installar nix: sh <(curl -L https://nixos.org/nix/install) --no-daemon
adicionar nix ao path: export PATH=$HOME/.nix-profile/bin:$PATH
Carregar configuração do nix: source ~/.bashrc
Verificar instalação do nix: nix-env --version
Iniciar o nix: nix-shell
Configurar o projeto: cabal configure --enable-tests
Construir o projeto: cabal build
executar tests: cabal test

