# codewars/runner

Issue tracker for CodeRunner used on [Codewars][codewars] and [Qualified][qualified].

## Reporting Issues

Please report any language related issues here.  
For anything else about Codewars, please use [codewars/codewars.com].

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

<!--
TODO Move language docs to docs.codewars.com/languages/
-->

### Stable

- [C](https://github.com/codewars/codewars.com/wiki/Language-C)
- [C#](https://github.com/codewars/codewars.com/wiki/Language-C-Sharp)
- [C++](https://github.com/codewars/codewars.com/wiki/Language-Cpp)
- [Clojure](https://github.com/codewars/codewars.com/wiki/Language-Clojure)
- [CoffeeScript](https://github.com/codewars/codewars.com/wiki/Language-CoffeeScript)
- [Coq](https://github.com/codewars/codewars.com/wiki/Language-Coq)
- [Crystal](https://github.com/codewars/codewars.com/wiki/Language-Crystal)
- [Dart](https://github.com/codewars/codewars.com/wiki/Language-Dart)
- [Elixir](https://github.com/codewars/codewars.com/wiki/Language-Elixir)
- [F#](https://github.com/codewars/codewars.com/wiki/Language-F-Sharp)
- [Go](https://github.com/codewars/codewars.com/wiki/Language-Go)
- [Groovy](https://github.com/codewars/codewars.com/wiki/Language-Groovy)
- [Haskell](https://github.com/codewars/codewars.com/wiki/Language-Haskell)
- [Java](https://github.com/codewars/codewars.com/wiki/Language-Java)
- [JavaScript](https://github.com/codewars/codewars.com/wiki/Language-JavaScript)
- [Kotlin](https://github.com/codewars/codewars.com/wiki/Language-Kotlin)
- [Lean](https://github.com/codewars/codewars.com/wiki/Language-Lean)
- [Lua](https://github.com/codewars/codewars.com/wiki/Language-Lua)
- [NASM](https://github.com/codewars/codewars.com/wiki/Language-NASM)
- [PHP](https://github.com/codewars/codewars.com/wiki/Language-PHP)
- [Python](https://github.com/codewars/codewars.com/wiki/Language-Python)
- [Racket](https://github.com/codewars/codewars.com/wiki/Language-Racket)
- [Ruby](https://github.com/codewars/codewars.com/wiki/Language-Ruby)
- [Rust](https://github.com/codewars/codewars.com/wiki/Language-Rust)
- [Scala](https://github.com/codewars/codewars.com/wiki/Language-Scala)
- [Shell](https://github.com/codewars/codewars.com/wiki/Language-Shell)
- [SQL](https://github.com/codewars/codewars.com/wiki/Language-SQL)
- [Swift](https://github.com/codewars/codewars.com/wiki/Language-Swift)
- [TypeScript](https://github.com/codewars/codewars.com/wiki/Language-TypeScript)

### Beta

- [Agda](https://github.com/codewars/codewars.com/wiki/Language-Agda)
- [BF](https://github.com/codewars/codewars.com/wiki/Language-BF)
- [CFML](https://github.com/codewars/codewars.com/wiki/Language-CFML)
- [COBOL](https://github.com/codewars/codewars.com/wiki/Language-COBOL)
- [CommonLisp](https://github.com/codewars/codewars.com/wiki/Language-CommonLisp)
- [Elm](https://github.com/codewars/codewars.com/wiki/Language-Elm)
- [Erlang](https://github.com/codewars/codewars.com/wiki/Language-Erlang)
- [Factor](https://github.com/codewars/codewars.com/wiki/Language-Factor)
- [Forth](https://github.com/codewars/codewars.com/wiki/Language-Forth)
- [Fortran](https://github.com/codewars/codewars.com/wiki/Language-Fortran)
- [Haxe](https://github.com/codewars/codewars.com/wiki/Language-Haxe)
- [Idris](https://github.com/codewars/codewars.com/wiki/Language-Idris)
- [Julia](https://github.com/codewars/codewars.com/wiki/Language-Julia)
- [Nim](https://github.com/codewars/codewars.com/wiki/Language-Nim)
- [Objective-C](https://github.com/codewars/codewars.com/wiki/Language-Objective-C)
- [OCaml](https://github.com/codewars/codewars.com/wiki/Language-OCaml)
- [Pascal](https://github.com/codewars/codewars.com/wiki/Language-Pascal)
- [Perl](https://github.com/codewars/codewars.com/wiki/Language-Perl)
- [PowerShell](https://github.com/codewars/codewars.com/wiki/Language-PowerShell)
- [Prolog](https://github.com/codewars/codewars.com/wiki/Language-Prolog)
- [PureScript](https://github.com/codewars/codewars.com/wiki/Language-PureScript)
- [R](https://github.com/codewars/codewars.com/wiki/Language-R)
- [Raku](https://github.com/codewars/codewars.com/wiki/Language-Raku)
- [Reason](https://github.com/codewars/codewars.com/wiki/Language-Reason)
- [Solidity](https://github.com/codewars/codewars.com/wiki/Language-Solidity)
- [VB.NET](https://github.com/codewars/codewars.com/wiki/Language-VB)

### Partial (No Test Support)

- D

### Requested

See issues [with language request label][language-requests].

## Feature Requests

Please open new issues using appropriate issue templates.

[codewars]: https://www.codewars.com
[qualified]: https://www.qualified.io
[codewars/codewars.com]: https://github.com/codewars/codewars.com
[qualified-dockerhub]: https://hub.docker.com/u/qualified
[help-wanted]: https://github.com/codewars/runner/issues?q=label%3A%22help+wanted%22+is%3Aissue+is%3Aopen+sort%3Aupdated-desc
[code-runner-projects]: https://github.com/search?q=topic%3Acode-runner+org%3Acodewars&type=Repositories
[language-requests]: https://github.com/codewars/runner/issues?q=is%3Aissue+is%3Aopen+sort%3Aupdated-desc+label%3Arequest%2Flanguage
