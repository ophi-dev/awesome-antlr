# Awesome ANTLR [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources for [ANTLR](https://www.antlr.org) (ANother Tool for Language Recognition) — the parser generator, its runtimes across languages, the algorithms behind it, tooling, and real-world grammars.

ANTLR generates lexers and parsers from a single grammar (`.g4`) file, using the adaptive `ALL(*)` parsing strategy. This list gathers the foundational research, the runtime targets for each language, editor/analysis tooling, and a catalogue of production grammars published by their vendors.

> "ANTLR uses the LL(\*) parsing strategy… (it) can handle grammars that are not LL(k) by performing an infinite lookahead… ideal for parsing more complex grammars with multiple viable paths."
>
> — Latif et al., *Comparison of Leading Language Parsers* (ICSTE 2023)

## Contents

- [Foundations](#foundations)
  - [Papers](#papers)
  - [Books](#books)
- [The Tool](#the-tool)
- [Runtime Targets](#runtime-targets)
- [Tooling](#tooling)
- [Grammars](#grammars)
  - [Grammar Collections](#grammar-collections)
  - [Vendor-Published Grammars](#vendor-published-grammars)
  - [Community Grammars](#community-grammars)
- [Benchmarks](#benchmarks)
- [Learning](#learning)

## Foundations

### Papers

- [Adaptive LL(*) Parsing: The Power of Dynamic Analysis](https://doi.org/10.1145/2660193.2660202) - Terence Parr, Sam Harwell, Kathleen Fisher. OOPSLA 2014. The paper introducing `ALL(*)`, the parsing strategy at the heart of ANTLR 4.
- [LL(*): The Foundation of the ANTLR Parser Generator](https://doi.org/10.1145/1993498.1993548) - Terence Parr, Kathleen Fisher. PLDI 2011. The `LL(*)` algorithm behind ANTLR 3.
- [ANTLR: A Predicated-LL(k) Parser Generator](https://doi.org/10.1002/spe.4380250705) - Terence J. Parr, Russell W. Quong. Software: Practice and Experience, 1995. The original paper describing ANTLR's design.
- [ANTLRWorks: An ANTLR Grammar Development Environment](https://doi.org/10.1002/spe.872) - Jean Bovet, Terence Parr. Software: Practice and Experience, 2008. The grammar IDE with live parse-tree visualization.
- [An Empirical Evaluation of Lex/Yacc and ANTLR Parser Generation Tools](https://doi.org/10.1371/journal.pone.0264326) - Francisco Ortin, Jose Quiroga, Oscar Rodriguez-Prieto, Miguel Garcia. PLOS ONE, 2022. An independent, open-access comparison of ANTLR against Lex/Yacc.
- [Comparison of Leading Language Parsers – ANTLR, JavaCC, SableCC, Tree-sitter, Yacc, Bison](https://doi.org/10.1109/icste61649.2023.00009) - Afshan Latif, Farooque Azam, Muhammad Waseem Anwar, Amina Zafar. ICSTE 2023. A survey comparing ANTLR against other major parser generators.

### Books

- [The Definitive ANTLR 4 Reference](https://pragprog.com/titles/tpantlr2/the-definitive-antlr-4-reference/) - Terence Parr. Pragmatic Bookshelf, 2013 (ISBN 978-1-934356-99-9). The canonical guide to ANTLR 4.
- [Language Implementation Patterns](https://pragprog.com/titles/tpdsl/language-implementation-patterns/) - Terence Parr. Pragmatic Bookshelf, 2009 (ISBN 978-1-934356-45-6). Techniques for building parsers, interpreters, and translators.

## The Tool

- [antlr/antlr4](https://github.com/antlr/antlr4) - The reference parser generator and its bundled Java, C#, C++, Go, Python, JavaScript, Dart, and Swift runtimes.
- [antlr-ng](https://github.com/antlr-ng/antlr-ng) - Next-generation TypeScript reimplementation of the ANTLR tool.
- [ANTLR Lab](https://github.com/antlr/antlr4-lab) - Browser-based playground to write grammars and visualize parse trees.

## Runtime Targets

The reference runtimes for Java, C#, C++, Go, Python3, JavaScript, Dart, and Swift ship inside [antlr/antlr4](https://github.com/antlr/antlr4/tree/master/runtime). Notable independent or optimized targets:

- [antlr4-go/antlr](https://github.com/antlr4-go/antlr) - The Go target, published as a standalone Go module.
- [antlr4ng](https://github.com/mike-lischke/antlr4ng) - Modern TypeScript/JavaScript runtime.
- [antlr4cs](https://github.com/tunnelvisionlabs/antlr4cs) - Highly-optimized alternative C# target.
- [antlr-php-runtime](https://github.com/antlr/antlr-php-runtime) - Official PHP runtime.
- [antlr-rust-runtime](https://github.com/ophi-dev/antlr-rust-runtime) - Pure-Rust runtime and `.g4` code generator, no JVM required at build time.
- [antlr4wasm](https://github.com/mike-lischke/antlr4wasm) - WebAssembly target for ANTLR4, with a TypeScript interface.
- [antlr-kotlin](https://github.com/Strumenta/antlr-kotlin) - Kotlin target for ANTLR 4, including Kotlin Multiplatform support.

## Tooling

- [antlr4-c3](https://github.com/mike-lischke/antlr4-c3) - Grammar-agnostic code-completion engine for ANTLR-based parsers.
- [vscode-antlr4](https://github.com/mike-lischke/vscode-antlr4) - Visual Studio Code extension: syntax highlighting, railroad diagrams, ATN visualization, debugging.
- [intellij-plugin-v4](https://github.com/antlr/intellij-plugin-v4) - ANTLR v4 plugin for IntelliJ IDEA: live grammar preview and parse-tree inspection.
- [ANTLR4ParseTreeVisualizer](https://github.com/zspitz/ANTLR4ParseTreeVisualizer) - Visual Studio debugging visualizer and .NET controls for ANTLR 4 parse trees.
- [Grun.Net](https://github.com/wiredwiz/Grun.Net) - A .NET toolset for testing and diagnosing ANTLR 4 grammars, a TestRig alternative for C# parsers.
- [Grammarinator](https://github.com/renatahodovan/grammarinator) - A grammar-based test generator (fuzzer) that produces random inputs from an ANTLR 4 grammar.
- [rules_antlr](https://github.com/marcohu/rules_antlr) - Bazel build rules for running ANTLR on your grammars.

## Grammars

### Grammar Collections

- [grammars-v4](https://github.com/antlr/grammars-v4) - The community collection of ANTLR 4 grammars for dozens of languages (action-free, portable).

### Vendor-Published Grammars

Grammars maintained by the language/product's own project — first-hand, authoritative sources:

- [Kotlin](https://github.com/Kotlin/kotlin-spec/tree/release/grammar/src/main/antlr) - Official grammar from the Kotlin Language Specification (JetBrains).
- [MySQL](https://github.com/mysql/mysql-shell-plugins) - Oracle's official MySQL grammar (`MySQLParser.g4` / `MySQLLexer.g4`), used by MySQL Shell.
- [GQL](https://github.com/opengql/grammar) - ANTLR grammar for the ISO/IEC 39075 Graph Query Language. See also [TuGraph-family/gql-grammar](https://github.com/TuGraph-family/gql-grammar).
- [Apache Avro IDL](https://github.com/apache/avro/blob/main/share/idl_grammar/org/apache/avro/idl/Idl.g4) - The grammar for Avro's interface description language.
- [Apache Groovy](https://github.com/apache/groovy/tree/master/src/antlr) - The official grammar for the Groovy language (`GroovyParser.g4` / `GroovyLexer.g4`).
- [Apache Spark SQL](https://github.com/apache/spark/tree/master/sql/api/src/main/antlr4/org/apache/spark/sql/catalyst/parser) - Spark's SQL dialect grammar (`SqlBaseParser.g4`).
- [Trino SQL](https://github.com/trinodb/trino/blob/master/core/trino-grammar/src/main/antlr4/io/trino/grammar/sql/SqlBase.g4) - The SQL grammar for the Trino query engine.
- [Presto SQL](https://github.com/prestodb/presto/blob/master/presto-parser/src/main/antlr4/com/facebook/presto/sql/parser/SqlBase.g4) - The SQL grammar for the Presto query engine.
- [AWS DQDL](https://github.com/awslabs/dqdl) - Grammar for the Data Quality Definition Language used by AWS Glue Data Quality.

### Community Grammars

Notable standalone grammars maintained by the community:

- [tsqlparser](https://github.com/jimidle/tsqlparser) - A T-SQL (SQL Server 2008 R2) grammar for ANTLR 4.
- [cedar-antlr-grammar](https://github.com/iann0036/cedar-antlr-grammar) - An ANTLR grammar for the AWS Cedar policy language.
- [solidity-antlr4](https://github.com/solidityj/solidity-antlr4) - A grammar for the Solidity smart-contract language.
- [TypeCobol](https://github.com/TypeCobolTeam/TypeCobol/tree/develop/TypeCobol/AntlrGrammar) - ANTLR grammars for IBM Enterprise COBOL, from an incremental COBOL parser.
- [quoteparser](https://github.com/quoteparser/grammar/tree/master/src/main/antlr4/com/quoteparser) - A grammar for parsing FX option quotes, a neat example of parsing a non-programming-language notation.

## Benchmarks

- [antlr4-runtime-benchmarks](https://github.com/mike-lischke/antlr4-runtime-benchmarks) - Cross-runtime performance benchmarks comparing ANTLR targets on the same grammars and inputs.

## Learning

- [ANTLR Documentation](https://github.com/antlr/antlr4/blob/master/doc/index.md) - The official documentation, from getting started to grammar reference.
- [ANTLR Mega Tutorial](https://tomassetti.me/antlr-mega-tutorial/) - A long-form practical introduction to building parsers with ANTLR.
- [ANTLR Grammar Optimisation: What Worked and What Didn't](https://www.atfinity.swiss/articles/antlr-grammar-optimisation-what-worked-and-what-didnt) - A practical writeup of real-world techniques for speeding up ANTLR grammars.
- [Testing Grammar Using ANTLR4 TestRig (grun)](https://bobinsingla.wordpress.com/2016/04/29/testing-grammar-using-antlr4-testrig-grun/) - A hands-on guide to validating grammars with ANTLR's TestRig/grun tool.

## Contributing

Contributions welcome! Please read the [contribution guidelines](contributing.md) first. Entries must be genuinely useful, accurately described, and point to a real, maintained resource.
