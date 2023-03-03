# Guide de style Python de Google
![](https://img.shields.io/badge/contact-dr.mokira%40gmail.com-blueviolet)
![](https://img.shields.io/badge/lastest-2023--03--03-success)
![](https://img.shields.io/badge/status-en%20r%C3%A9daction%20-yellow)

<details>
  <summary>Table of Contents</summary>

  <ul>
    <li><a href="#s1-background">1 Background</a></li>
    <li><a href="#s2-python-language-rules">2 Python Language Rules</a>
      <ul>
        <li><a href="#s2.1-lint">2.1 Lint</a></li>
        <li><a href="#s2.2-imports">2.2 Imports</a></li>
        <li><a href="#s2.3-packages">2.3 Packages</a></li>
        <li><a href="#s2.4-exceptions">2.4 Exceptions</a></li>
        <li><a href="#s2.5-global-variables">2.5 Mutable Global State</a></li>
        <li><a href="#s2.6-nested">2.6 Nested/Local/Inner Classes and Functions</a></li>
        <li><a href="#s2.7-comprehensions">2.7 Comprehensions &amp; Generator Expressions</a></li>
        <li><a href="#s2.8-default-iterators-and-operators">2.8 Default Iterators and Operators</a></li>
        <li><a href="#s2.9-generators">2.9 Generators</a></li>
        <li><a href="#s2.10-lambda-functions">2.10 Lambda Functions</a></li>
        <li><a href="#s2.11-conditional-expressions">2.11 Conditional Expressions</a></li>
        <li><a href="#s2.12-default-argument-values">2.12 Default Argument Values</a></li>
        <li><a href="#s2.13-properties">2.13 Properties</a></li>
        <li><a href="#s2.14-truefalse-evaluations">2.14 True/False Evaluations</a></li>
        <li><a href="#s2.16-lexical-scoping">2.16 Lexical Scoping</a></li>
        <li><a href="#s2.17-function-and-method-decorators">2.17 Function and Method Decorators</a></li>
        <li><a href="#s2.18-threading">2.18 Threading</a></li>
        <li><a href="#s2.19-power-features">2.19 Power Features</a></li>
        <li><a href="#s2.20-modern-python">2.20 Modern Python: from __future__ imports</a></li>
        <li><a href="#s2.21-type-annotated-code">2.21 Type Annotated Code</a></li>
      </ul>
    </li>
    <li><a href="#s3-python-style-rules">3 Python Style Rules</a>
      <ul>
        <li><a href="#s3.1-semicolons">3.1 Semicolons</a></li>
        <li><a href="#s3.2-line-length">3.2 Line length</a></li>
        <li><a href="#s3.3-parentheses">3.3 Parentheses</a></li>
        <li><a href="#s3.4-indentation">3.4 Indentation</a>
          <ul>
            <li><a href="#s3.4.1-trailing-commas">3.4.1 Trailing commas in sequences of items?</a></li>
          </ul>
        </li>
        <li><a href="#s3.5-blank-lines">3.5 Blank Lines</a></li>
        <li><a href="#s3.6-whitespace">3.6 Whitespace</a></li>
        <li><a href="#s3.7-shebang-line">3.7 Shebang Line</a></li>
        <li><a href="#s3.8-comments-and-docstrings">3.8 Comments and Docstrings</a>
          <ul>
            <li><a href="#s3.8.1-comments-in-doc-strings">3.8.1 Docstrings</a></li>
            <li><a href="#s3.8.2-comments-in-modules">3.8.2 Modules</a></li>
            <li><a href="#s3.8.2.1-test-modules">3.8.2.1 Test modules</a></li>
            <li><a href="#s3.8.3-functions-and-methods">3.8.3 Functions and Methods</a></li>
            <li><a href="#s3.8.4-comments-in-classes">3.8.4 Classes</a></li>
            <li><a href="#s3.8.5-block-and-inline-comments">3.8.5 Block and Inline Comments</a></li>
            <li><a href="#s3.8.6-punctuation-spelling-and-grammar">3.8.6 Punctuation, Spelling, and Grammar</a></li>
          </ul>
        </li>
        <li><a href="#s3.10-strings">3.10 Strings</a>
          <ul>
            <li><a href="#s3.10.1-logging">3.10.1 Logging</a></li>
            <li><a href="#s3.10.2-error-messages">3.10.2 Error Messages</a></li>
          </ul>
        </li>
        <li><a href="#s3.11-files-sockets-closeables">3.11 Files, Sockets, and similar Stateful Resources</a></li>
        <li><a href="#s3.12-todo-comments">3.12 TODO Comments</a></li>
        <li><a href="#s3.13-imports-formatting">3.13 Imports formatting</a></li>
        <li><a href="#s3.14-statements">3.14 Statements</a></li>
        <li><a href="#s3.15-accessors">3.15 Accessors</a></li>
        <li><a href="#s3.16-naming">3.16 Naming</a>
          <ul>
            <li><a href="#s3.16.1-names-to-avoid">3.16.1 Names to Avoid</a></li>
            <li><a href="#s3.16.2-naming-conventions">3.16.2 Naming Conventions</a></li>
            <li><a href="#s3.16.3-file-naming">3.16.3 File Naming</a></li>
            <li><a href="#s3.16.4-guidelines-derived-from-guidos-recommendations">3.16.4 Guidelines derived from Guido’s Recommendations</a></li>
          </ul>
        </li>
        <li><a href="#s3.17-main">3.17 Main</a></li>
        <li><a href="#s3.18-function-length">3.18 Function length</a></li>
        <li><a href="#s3.19-type-annotations">3.19 Type Annotations</a>
          <ul>
            <li><a href="#s3.19.1-general-rules">3.19.1 General Rules</a></li>
            <li><a href="#s3.19.2-line-breaking">3.19.2 Line Breaking</a></li>
            <li><a href="#s3.19.3-forward-declarations">3.19.3 Forward Declarations</a></li>
            <li><a href="#s3.19.4-default-values">3.19.4 Default Values</a></li>
            <li><a href="#s3.19.5-nonetype">3.19.5 NoneType</a></li>
            <li><a href="#s3.19.6-type-aliases">3.19.6 Type Aliases</a></li>
            <li><a href="#s3.19.7-ignoring-types">3.19.7 Ignoring Types</a></li>
            <li><a href="#s3.19.8-typing-variables">3.19.8 Typing Variables</a></li>
            <li><a href="#s3.19.9-tuples-vs-lists">3.19.9 Tuples vs Lists</a></li>
            <li><a href="#s3.19.10-typevars">3.19.10 Type variables</a></li>
            <li><a href="#s3.19.11-string-types">3.19.11 String types</a></li>
            <li><a href="#s3.19.12-imports-for-typing">3.19.12 Imports For Typing</a></li>
            <li><a href="#s3.19.13-conditional-imports">3.19.13 Conditional Imports</a></li>
            <li><a href="#s3.19.14-circular-dependencies">3.19.14 Circular Dependencies</a></li>
            <li><a href="#s3.19.15-generics">3.19.15 Generics</a></li>
            <li><a href="#s3.19.16-build-dependencies">3.19.16 Build Dependencies</a></li>
          </ul>
        </li>
      </ul>
    </li>
    <li><a href="#4-parting-words">4 Parting Words</a></li>
  </ul>

</details>

