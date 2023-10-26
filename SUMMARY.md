# Table of contents

* [Qso](README.md)
  * [Articles](readme/articles.md)
* [Anxious](anxious.md)

## David

* [Small Talk](david/small-talk.md)
* [Development](david/development.md)
* [Authentication](david/authentication.md)
* [Validation](david/validation.md)
* [Integration](david/integration.md)
* [Delivery](david/delivery.md)

## Symbol Interpretation

* [Object-Oriented Programming](symbol-interpretation/object-oriented-programming/README.md)
  * [Encapsulation](symbol-interpretation/object-oriented-programming/encapsulation.md)
  * [Abstraction](symbol-interpretation/object-oriented-programming/abstraction.md)
  * [Inheritance](symbol-interpretation/object-oriented-programming/inheritance.md)
  * [Polymorphism](symbol-interpretation/object-oriented-programming/polymorphism.md)
* [Functional Programming](symbol-interpretation/functional-programming/README.md)
  * [First-Class Function](symbol-interpretation/functional-programming/first-class-function.md)
  * [Closure](symbol-interpretation/functional-programming/closure.md)
  * [Monad](symbol-interpretation/functional-programming/monad.md)
  * [Side Effect](symbol-interpretation/functional-programming/side-effect.md)
  * [Lazy Evaluation](symbol-interpretation/functional-programming/lazy-evaluation.md)
* [Syntax](symbol-interpretation/syntax/README.md)
  * [Desugar](symbol-interpretation/syntax/desugar.md)
  * [Pattern Matching](symbol-interpretation/syntax/pattern-matching.md)
* [Type System](symbol-interpretation/type-system/README.md)
  * [Substructural Type System](symbol-interpretation/type-system/substructural-type-system.md)
  * [Type Complexity](symbol-interpretation/type-system/type-complexity/README.md)
    * [Algebraic Data Type](symbol-interpretation/type-system/type-complexity/algebraic-data-type.md)
  * [Type Inference](symbol-interpretation/compilation/type-inference.md)
  * [Duck Type](symbol-interpretation/type-system/duck-type.md)
  * [Generic Type](symbol-interpretation/type-system/generic-type.md)
  * [None Type](symbol-interpretation/type-system/none-type.md)
* [Interpretation](symbol-interpretation/interpretation/README.md)
  * [Encode / Decode](symbol-interpretation/interpretation/encode-decode.md)
* [Compilation](symbol-interpretation/compilation/README.md)
  * [JIT](symbol-interpretation/compilation/just-in-time-compilation.md)
* [Optimization](symbol-interpretation/optimization/README.md)
  * [Bounds-Checking Elimination](symbol-interpretation/optimization/bounds-checking-elimination.md)
  * [Common Sub-Expression Elimination](symbol-interpretation/optimization/common-sub-expression-elimination.md)
* [Discussion](symbol-interpretation/discussion.md)
  * [GaGaGa](symbol-interpretation/discussion/gagaga.md)
* [References](symbol-interpretation/references.md)

***

* [LLVM](llvm/README.md)
  * [MLIR](llvm/mlir.md)
  * [LLVM IR](llvm/llvm-ir.md)

## Design Pattern

* [Visitor](design-pattern/visitor/README.md)
  * [Dispatch](design-pattern/visitor/dispatch.md)

## Runtime

* [Design (Strategy)](runtime/design-strategy.md)
* [System Iteraction](runtime/system-iteraction/README.md)
  * [Process](runtime/system-iteraction/process.md)
  * [Thread (Kernel)](runtime/system-iteraction/thread-kernel.md)
  * [Thread (User)](runtime/system-iteraction/thread-user.md)
* [Industrial Practice](runtime/industrial-practice/README.md)
  * [Asynchronous](runtime/industrial-practice/asynchronous.md)
  * [Concurrency](runtime/industrial-practice/concurrency.md)
  * [Parallel Computing](runtime/industrial-practice/parallel-computing.md)
* [Stack / Heap Tracing](runtime/stack-heap-tracing.md)
* [Exception Handling](symbol-interpretation/runtime/exception-handling.md)
* [Gabbage Collection](symbol-interpretation/runtime/gabbage-collection.md)

## Language Analysis

* [C++](language-analysis/c++.md)
  * [Destructor](language-analysis/c++/destructor.md)
  * [Memory Management](language-analysis/c++/memory-management.md)
  * [Rvalue Reference](language-analysis/c++/rvalue-reference.md)
* [Java](language-analysis/java/README.md)
  * [JVM - GC](language-analysis/java/jvm-gc.md)
  * [Kotlin](language-analysis/java/kotlin.md)
  * [Scala](language-analysis/java/scala.md)
* [JavaScript](language-analysis/javascript.md)
* [Rust](language-analysis/rust.md)
* [Go](language-analysis/go.md)
* [Swift](language-analysis/swift.md)
* [C#](language-analysis/c/README.md)
  * [Syntax](language-analysis/c.md)
* [Meta Language](meta-language/README.md)
  * [Lisp](meta-language/lisp.md)
  * [Haskell](meta-language/haskell.md)
  * [Ocaml](meta-language/ocaml.md)
  * [F#](meta-language/f.md)
* [Script Language](language-analysis/script-language/README.md)
  * [Python](language-analysis/script-language/python.md)
  * [Ruby](language-analysis/script-language/ruby.md)
  * [Julia](language-analysis/script-language/julia.md)
* [DSL](dsl/README.md)
  * [SQL](dsl/sql.md)
  * [MongoDB](dsl/mongodb.md)
  * [Logica](dsl/logica.md)

## Others

* [Computability](others/computability/README.md)
  * [Primitive Recursive Function](others/computability/primitive-recursive-function.md)

## Operating System

* [eBPF](operating-system/ebpf.md)
* [POSIX](framework-analysis/standard/posix.md)

## Framework Analysis

* [Overview](resource-dispatch/overview.md)
* [LLVM](framework-analysis/llvm/README.md)
  * [Clang](framework-analysis/llvm/clang.md)
  * [LLVM IR](framework-analysis/llvm/llvm-ir.md)
  * [MLIR](framework-analysis/llvm/mlir.md)
* [Computing Optimization](framework-analysis/computing-optimization/README.md)
  * [SIMD](framework-analysis/computing-optimization/simd.md)
  * [oneTBB (MIMD)](framework-analysis/computing-optimization/onetbb-mimd.md)
  * [OpenMP (MIMD)](framework-analysis/computing-optimization/openmp-mimd.md)
  * [Discussion](framework-analysis/computing-optimization/discussion.md)
* [Distributed System](framework-analysis/distributed-system/README.md)
  * [MPI](framework-analysis/distributed-system/mpi.md)

## Database Analysis

* [DBMS Essential](basic-concept/dbms-essential.md)
* [MySQL](database-analysis/mysql/README.md)
  * [线程池 (Thread Pool)](database-analysis/mysql/xian-cheng-chi-thread-pool.md)
  * [查询缓存 (Query Cache)](database-analysis/mysql/cha-xun-huan-cun-query-cache.md)
  * [CRUD](database-analysis/mysql/crud/README.md)
    * [Create](database-analysis/mysql/crud/create.md)
    * [Read](database-analysis/mysql/crud/read.md)
    * [Update](database-analysis/mysql/crud/update.md)
    * [Delete](database-analysis/mysql/crud/delete.md)

## High-Performance Computing

* [Overview](cluster-evolution/overview.md)
* [Batch Computing](basic-concept/data-computation.md)
* [Stream Computing](high-performance-computing/stream-computing.md)
* [Interactive Computing](high-performance-computing/interactive-computing.md)
* [Graph Computing](high-performance-computing/graph-computing.md)

## Resource Dispatch

* [Overview](framework-analysis/overview.md)

## Cluster Evolution

* [Overview](high-performance-computing/overview.md)

## Distributed System

* [Async. Comm.](distributed-system/async.-comm..md)
* [Fundamental](distributed-system/fundamental/README.md)
  * [CAP Theorem](distributed-system/fundamental/cap-theorem.md)

## 八股文 (散装)

* [Data Structure](ba-gu-wen-san-zhuang/data-structure.md)

## Useful Tools

* [FileCheck](useful-tools/filecheck.md)

## Experiences

* [Docker](experiences/docker/README.md)
  * [Useful Commands](experiences/docker/useful-commands.md)
  * [Source Configuration](experiences/docker/source-configuration.md)
  * [Get Image](experiences/docker/get-image.md)

***

* [乱七八糟](luan-qi-ba-zao/README.md)
  * [科普账号](luan-qi-ba-zao/ke-pu-zhang-hao.md)
