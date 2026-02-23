---
layout: post
title: "Choose your weapon"
date: 2026-02-23 20:00:00 +0000
categories: programming languages
---

In olden times, when discussions escalated beyond the exchange of heated words, they would sometimes resort to a method that would settle the matter for good. The challenger would propose a duel, and the challenged party often had the right to choose the weapon. The opposing duellist knew that the right tool could mean the difference between being right or being dead.

While the stakes are somewhat less dramatic these days, the principle still applies when starting a new software project. Programmers don't often get a choice of the problem to solve, so they must adopt a technological stack that will maximise the chances of success. Just as a skilled duellist would commit to a weapon that played to their strengths and the weaknesses of their opponent, it stands to reason that a seasoned developer would select a language which aligns with the problem domain and the project's requirements.

Choosing a language that aligns with the domain's fundamental requirements can lead to cleaner code, better performance, and a more enjoyable development experience. However, the programming language selection is often influenced more by the ecosystem than by the language's intrinsic suitability for the task. It is therefore easy to mistake a language's ecosystem for evidence of its natural strengths.

But ecosystems grow for many reasons: historical accidents, corporate backing, community momentum, or the need to patch over a language's weaknesses. When we look at the major programming languages through this lens, a more interesting picture emerges: the places where a language thrives are not always the places where it fits. And when new technological domains appear, the mismatch between intrinsic language design and ecosystem inertia becomes even more visible.

The most popular ecosystems in software development tend to form around languages that were in the right place at the right time. JavaScript became the language of the web not because it was the best language for UI programming, but because it was the only interoperable language browsers converged on. Python became the language of machine learning not because it was fast or mathematically elegant, but because researchers found it easy to prototype in and wrapped the heavy lifting in C and Fortran. Java became the backbone of enterprise development not because Java's syntax or semantics were especially well-suited to building complex business systems, but because Sun Microsystems sold a compelling vision of portability and stability to large companies (the famous "Write once, run anywhere").

Ecosystems often grow where languages are weak. Spring exists because Java was too rigid and verbose for the kinds of applications enterprises wanted to build. Webpack and Babel exist because JavaScript lacked modules, types, and a coherent standard library. NumPy exists because Python is too slow to handle numerical computation directly. C++ template metaprogramming flourished because the language lacked a proper macro system and compile-time reflection.

When we strip away the ecosystems and look at the languages themselves--their type systems, runtime models, memory semantics, concurrency primitives, and syntactic affordances--we get a much clearer sense of what each language is intrinsically suited for. And this becomes especially important when we look at emerging domains, where ecosystems are still forming and languages are forced to stand on their own design foundations.

WebAssembly rewards languages that produce small, predictable binaries and have clear, explicit memory models. Rust, C, C++, and Zig feel at home here because their semantics map directly onto WASM's linear memory and sandboxed execution. They don't rely on garbage collectors, runtime reflection, or dynamic dispatch mechanisms that require large support libraries. They compile down to compact, deterministic code that fits the constraints of the WASM environment.

Languages like Java, C#, and Go can target WASM, but they bring baggage: garbage collectors, runtime metadata, and expectations about threading or system calls that don't map cleanly to the WASM model. Python and Ruby can run in WASM only by dragging along large compatibility layers that simulate their dynamic runtimes. The difference between "runs on WASM" and "belongs on WASM" becomes obvious.

AI agents, differentiable programming, and symbolic reasoning reward languages that are dynamic, reflective, and comfortable with loosely structured data. Python thrives here not because it is fast or elegant, but because its dynamic nature makes it easy to express algorithms in a way that feels close to pseudocode. Julia goes further by making mathematical abstractions first-class citizens and allowing the compiler to optimize them aggressively. Lisp and Clojure feel native for symbolic computation because their code-as-data model makes it trivial to manipulate programs as structures, which AI agents often need to do.

These languages don't just support AI ecosystems; they align with the mental model of AI work. They allow programs to modify themselves, generate new behavior at runtime, and operate on heterogeneous data without ceremony. They feel like languages designed for thinking, not just coding.

Distributed systems expose the mismatch between language semantics and real-world concurrency. Go, Erlang, and Elixir stand out because their concurrency models are built into the language itself, and need fewer framework-level contortions to express concurrency. Goroutines and channels in Go make concurrent programming feel natural and lightweight. Erlang's actor model, with its supervision trees and message passing, was designed for fault-tolerant telecom systems long before microservices became fashionable.

Rust also fits this domain, though in a different way. Its ownership and borrowing rules prevent data races in safe Rust at compile time, enabling highly concurrent systems with strong memory-safety guarantees.

Languages like Python can build distributed systems, but they rely heavily on frameworks to compensate for their concurrency limitations. The language offers fewer built-in primitives for CPU-parallel workloads, so its ecosystems fill the gap.

Security-critical domains reveal the limits of languages that rely on conventions or tooling to avoid memory errors. Rust and Ada/SPARK stand out because they provide safety guarantees at the language level. Rust's ownership model eliminates entire classes of memory bugs in safe code. Ada/SPARK supports formal proof of specified properties. These languages help developers by making writing unsafe code cumbersome enough to discourage it.

C and C++ dominate legacy security-critical systems because of historical momentum, not because they are well-suited to the task. Their ecosystems are full of sanitizers, linters, and static analyzers precisely because the languages themselves offer little in the way of protection.

Modern data pipelines depend on predictable memory layouts, SIMD-friendly structures, and zero-copy semantics. Rust, C++, and Julia align naturally with these requirements. C++ remains the backbone of high-performance data engines because it allows fine-grained control over memory and CPU instructions. Julia's JIT compiler can generate highly optimized code for numerical kernels while keeping the syntax expressive. Python's ubiquity in data science is in no small part due to its ecosystem, not because it fits the domain. In many production stacks, the heaviest computation happens in compiled libraries (often C, C++, Fortran, and increasingly Rust), while Python acts as the glue.

Edge and IoT environments expose the cost of runtime overhead. Devices with limited memory, power, and compute capacity often struggle with garbage collectors, large runtimes, or unpredictable latency. C, Rust, and Zig feel native here because they produce tiny binaries and give developers explicit control over memory and performance. They map directly to the constraints of the hardware. Languages with heavy runtimes can be made to work in these environments, but often by bending the environment to accommodate the language, rather than the other way around.

Across all these domains, a consistent pattern emerges. Languages that accumulate large ecosystems for a domain are not always naturally suited to it; sometimes developers build tools to compensate for the language's shortcomings. JavaScript's build tools exist because the language lacked modules and types. Java's enterprise frameworks exist because the language was too rigid for real-world business logic. Python's scientific stack exists because the language is too slow for numerical computation.

When a language is intrinsically suited to a domain, the ecosystem feels like an extension of the language's design. Ruby on Rails feels like Ruby. Erlang's OTP feels like Erlang. Rust's async ecosystem feels like Rust. These ecosystems don't fight the language; they express it.

When a language is not suited to a domain, the ecosystem feels like a workaround. Spring feels like a workaround for Java. Webpack feels like a workaround for JavaScript. NumPy feels like a workaround for Python. These ecosystems succeed because they are necessary, not because they are natural.

As new domains emerge--WebAssembly, AI agents, distributed systems, data pipelines, edge computing--the intrinsic properties of languages matter more than ever. Ecosystems will eventually grow around whatever languages developers choose, but the languages that feel native to these domains should shape the future more naturally and more sustainably.

If you have the choice, pick a language that feels like it belongs in the domain--learn it if need be. It might not be the most popular option today, but you may be helping make it one.
