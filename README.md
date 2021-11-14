# codewars/runner

Issue tracker for CodeRunner used on [Codewars][codewars] and [Qualified][qualified].

## Reporting Issues

Please report any language related issues here.  
For anything else about Codewars, please use [codewars/codewars.com].

## Feature Requests

Please open new issues using appropriate issue templates.

## Code

CodeRunner itself is not open source, but it's roughly equivalent to the following:

```bash
$ WORKDIR=/workspace/
# Create a container
$ C=$(docker container create --rm -w $WORKDIR language-image cmd args)
# Copy files
$ files | preprocess | docker container cp - $C:$WORKDIR
# Run
$ docker container start --attach $C | postprocess
```

- `WORKDIR` is not always `/workspace/` and can be a subdirectory of it (planned to be standardized in the future)
- `preprocess` is responsible for the file layout and any code modifications necessary for backwards compatibility (e.g., concatenation)
- `postprocess` transforms the output when necessary (e.g., Codewars test output from JSON)

Images can be used with local files by changing the step to copy the files:

```bash
$ docker container cp ./files/. $C:$WORKDIR
#                            ^^
#                            copy contents and not itself
```

Container images are available on [DockerHub under qualified][qualified-dockerhub].

## Contributing

Contributions are welcomed!

For now, please look at the following places:

- Issues [with `help wanted` label][help-wanted]
- Projects [with `code-runner` topic][code-runner-projects]

Feel free to open issues to ask us if you'd like to contribute in other ways.

## Supported Languages

### Stable

- [C](https://docs.codewars.com/languages/c)
- [C#](https://docs.codewars.com/languages/csharp)
- [C++](https://docs.codewars.com/languages/cpp)
- [Clojure](https://docs.codewars.com/languages/clojure)
- [CoffeeScript](https://docs.codewars.com/languages/coffeescript)
- [Coq](https://docs.codewars.com/languages/coq)
- [Crystal](https://docs.codewars.com/languages/crystal)
- [Dart](https://docs.codewars.com/languages/dart)
- [Elixir](https://docs.codewars.com/languages/elixir)
- [F#](https://docs.codewars.com/languages/fsharp)
- [Go](https://docs.codewars.com/languages/go)
- [Groovy](https://docs.codewars.com/languages/groovy)
- [Haskell](https://docs.codewars.com/languages/haskell)
- [Java](https://docs.codewars.com/languages/java)
- [JavaScript](https://docs.codewars.com/languages/javascript)
- [Kotlin](https://docs.codewars.com/languages/kotlin)
- [Lean](https://docs.codewars.com/languages/lean)
- [Lua](https://docs.codewars.com/languages/lua)
- [NASM](https://docs.codewars.com/languages/nasm)
- [PHP](https://docs.codewars.com/languages/php)
- [Python](https://docs.codewars.com/languages/python)
- [Racket](https://docs.codewars.com/languages/racket)
- [Ruby](https://docs.codewars.com/languages/ruby)
- [Rust](https://docs.codewars.com/languages/rust)
- [Scala](https://docs.codewars.com/languages/scala)
- [Shell](https://docs.codewars.com/languages/shell)
- [SQL](https://docs.codewars.com/languages/sql)
- [Swift](https://docs.codewars.com/languages/swift)
- [TypeScript](https://docs.codewars.com/languages/typescript)

### Beta

- [Agda](https://docs.codewars.com/languages/agda)
- [BF](https://docs.codewars.com/languages/bf)
- [CFML](https://docs.codewars.com/languages/cfml)
- [COBOL](https://docs.codewars.com/languages/cobol)
- [CommonLisp](https://docs.codewars.com/languages/commonlisp)
- [D](https://docs.codewars.com/languages/d)
- [Elm](https://docs.codewars.com/languages/elm)
- [Erlang](https://docs.codewars.com/languages/erlang)
- [Factor](https://docs.codewars.com/languages/factor)
- [Forth](https://docs.codewars.com/languages/forth)
- [Fortran](https://docs.codewars.com/languages/fortran)
- [Haxe](https://docs.codewars.com/languages/haxe)
- [Idris](https://docs.codewars.com/languages/idris)
- [Julia](https://docs.codewars.com/languages/julia)
- [Nim](https://docs.codewars.com/languages/nim)
- [Objective-C](https://docs.codewars.com/languages/objc)
- [OCaml](https://docs.codewars.com/languages/ocaml)
- [Pascal](https://docs.codewars.com/languages/pascal)
- [Perl](https://docs.codewars.com/languages/perl)
- [PowerShell](https://docs.codewars.com/languages/powershell)
- [Prolog](https://docs.codewars.com/languages/prolog)
- [PureScript](https://docs.codewars.com/languages/purescript)
- [R](https://docs.codewars.com/languages/r)
- [Raku](https://docs.codewars.com/languages/raku)
- [Reason](https://docs.codewars.com/languages/reason)
- [Solidity](https://docs.codewars.com/languages/solidity)
- [VB.NET](https://docs.codewars.com/languages/vb)

### Requested

See issues [with language request label][language-requests].

[codewars]: https://www.codewars.com
[qualified]: https://www.qualified.io
[codewars/codewars.com]: https://github.com/codewars/codewars.com
[qualified-dockerhub]: https://hub.docker.com/u/qualified
[help-wanted]: https://github.com/codewars/runner/issues?q=label%3A%22help+wanted%22+is%3Aissue+is%3Aopen+sort%3Aupdated-desc
[code-runner-projects]: https://github.com/search?q=topic%3Acode-runner+org%3Acodewars&type=Repositories
[language-requests]: https://github.com/codewars/runner/issues?q=is%3Aissue+is%3Aopen+sort%3Aupdated-desc+label%3Arequest%2Flanguage
