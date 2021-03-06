
# Astro Programming Language
#### Work in Progress :construction:
Current Version: 0.1.15

![astro screenshot](https://github.com/astrolang/astro/blob/develop/media/syntax_screenshot.png)

### What is Astro?
Astro is a fun programming language designed for safe _high-performance applications_. It is essentially a statically-typed systems language that
- facilitates rapid prototyping,
- features high-level abstractions with zero overhead,
- ensures memory safety without a (tracing) Garbage Collector, and
- supports data-race-free concurrency.

### Why create yet another programming language?
The language creator had a set of requirements (listed above) not met by any language ([Rust](https://en.wikipedia.org/wiki/Rust_(programming_language)) comes close). Although, the project started as an educational effort, it later shaped into a language designed to meet those requirements.

SIMD, threads and direct access to Web APIs are planned for WebAssembly. These and other proposals for GPU Compute will make the web a desirable HPC target in the near future. Astro is, for this reason, designed for high-performance apps that are expected to run on the server or in the browser.

In order to match up with the expressiveness and productivity of dynamic programming languages, Astro adds full type inference, structural typing, and some other high-level abstractions that reduce boilerplate code commonly associated with statically-typed languages. It feels like a scripting language for the most part.

#### Python
```python
def times(a, b):
    sum = a
    for i in range(b):
        sum += sum
    return sum
```
#### Astro
```kotlin
fun times(a, b) {
    var sum = a
    for i in range(b) {
        sum += sum
    }
    return sum
}
```

Astro is supposed to be high-level enough to write python-like scripts but also low-level enough to write an operating system kernel. Therefore, it doesn't have a traditional [garbage collector](https://en.m.wikipedia.org/wiki/Garbage_collection_(computer_science)) instead it relies on lifetime analysis at compile-time that free memory once they are no longer referenced.

Finally, seeing as CPU manufacturers are favoring multi-core design over transistor shrinkage, we believe making concurrency (and parallelism) a major aspect of the language development is beneficial to the type of applications that the language targets. Astro has built-in facilities for writing concurrent programs. A [CSP](https://en.m.wikipedia.org/wiki/Communicating_sequential_processes)-based lightweight threading model, with the guarantee that the programs you write won't have data races.

### How close is Astro to being ready for use?
Not close. Astro is at its infancy, there are several tasks —which you can find [below](#tasks)— to complete before it becomes usable.

For now, Astro can compile its source code to ast format. It is not ready for even the simplest application. It is also currently implemented Rust (it was being implemented in Javascript and C++), however, the plan is to bootstrap the compiler (implement it in Astro) once it is sufficiently well-featured.

### Where can I read about the language?
There is no throrough documentation for the language yet since the main implementation is still in active development, however, you can find an up-to-date summary of language features [here](docs/summary.ast).

### How do I install it?
N/A

### <a name="tasks"></a> What are the important tasks to complete?
- [x] ~Improve project structure~
- [x] ~Add automated unit testing and coverage reports~
- [x] ~Redesign and remove certain inconsistencies in language syntax~
- [x] ~Complete lexer implementation~
- [ ] Complete parser implementation
- [ ] Implement semantic analysis phase
- [ ] Create ambiguity finders for inheritance, multiple dispatch, etc.
- [ ] Implement type inference and garbage collection using program flow analysis
- [ ] Add wasm code generation
- [ ] Incorporate incremental compilation
- [ ] Build REPL
- [ ] Create specialized error handler

### Want to contribute to the project?
Please read the [code of conduct](CODE_OF_CONDUCT.md) and contribution [guidelines](CONTRIBUTING.md). We welcome your ideas and contributions.

### Do you have an unanswered question?
Please [open an issue](https://github.com/appcypher/astro/issues/new) and ask questions, offer to help, point out bugs or suggest features.

### Attributions
Astro logo made by [Freepik](https://www.freepik.com/)
