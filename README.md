## 업데이트
![example workflow name](https://github.com/gzupark/easy_rust_kor/workflows/github%20pages/badge.svg)

2021년 4월 2일: 이 글의 원저자에게 커피 한 잔 선물하기 위한 [BuyMeACoffee 링크 추가](https://www.buymeacoffee.com/mithridates).

2021년 2월 1일: [Now available on YouTube in English](https://www.youtube.com/playlist?list=PLfllocyHVgsRwLkTAhG0E-2QxCf-ozBkk) Two months later: all done as of 1 April 2021 for 186 videos in total (slightly over 23 hours).

2020년 12월 22일: 영어 버전 mdBook은 [여기](https://dhghomon.github.io/easy_rust)에서 확인 가능.

2021년 11월 27일: [한국어판 비디오](https://www.youtube.com/watch?v=W9DO6m8JSSs&list=PLfllocyHVgsSJf1zO6k6o3SX2mbZjAqYE) 녹화 시작!

2022년 5월 15일: 한국어판 비디오 [녹화 완료](https://www.reddit.com/r/rust/comments/upxumc/easy_rust_in_korean_on_youtube_is_basically_done/) (대략 총 24시간)!

![](Easy_Rust_sample_image.png)

## 들어가며
**[이 챕터를 YouTube에서 보기](https://youtu.be/W9DO6m8JSSs)**

Rust는 이미 좋은 교재가 있는 새로운 언어입니다. 그렇지만 간혹 그 교재들은 영어권 사람들을 위해 집필된 것으로 영어를 사용하지 않는 사람들에게는 어렵게 느껴질 것입니다. 근래에 많은 회사와 사람들이 Rust를 배우고 있고 쉬운 영어로 된 책을 통해 더 빠르게 배울 수 있습니다. 이 교재는 이런 회사들과 사람들이 간단한 영어(여기에서는 한국어)로 Rust를 배우기 위한 것입니다.

Rust는 새로운 언어지만 이미 아주 인기가 있습니다. 그 인기는 C 또는 C++의 속도와 제어 기능을 제공할 뿐만 아니라 Python과 같은 비교적 모던 언어의 메모리 안정성도 제공하기 때문입니다. 때로는 다른 언어와 다른 몇 가지 새로운 아이디어로 이를 수행합니다. 이것은 배워야하는 새로운 것들이 있다는 것을 의미하며, 단순히 "따라하면서 깨우치는 방법" 으로는 할 수 없습니다. Rust는 이해하기 위해서 잠시 생각해야 하는 언어입니다. 그러나 만약 다른 언어를 알고 있다면 꽤 친숙한 언어이고, 당신이 좋은 코드를 작성하는 데 도움을 줄 수 있습니다.

## 저자에 대해

저자는 한국에 거주하는 캐나다인으로 한국 회사에서 Rust를 쉽게 사용할 수 있는 방법을 고민하면서 Easy Rust를 집필했습니다. 영어를 모국어로 사용하지 않는 다른 나라들도 이 문서를 잘 사용하길 바랍니다.

## 한글로 배우는 Easy Rust

원문인 *Rust in Easy English*는 2020년 7월부터 8월까지 작성되었고, 그 분량은 400 페이지가 넘습니다. 질문이 있을 경우 저자의 [LinkedIn](https://www.linkedin.com/in/davemacleod) 또는 [Twitter](https://twitter.com/mithridates)로 연락할 수 있습니다. 잘못된 것이 보이거나 PR이 있다면 연락주세요. 20명이 넘는 사람들이 이미 코드의 오타와 문제를 수정하여 도움을 주었으므로 여러분도 가능합니다. 저자는 세계 최고의 Rust 전문가가 아니므로 항상 새로운 아이디어를 듣거나 책을 더 잘 만들 수 있는 길을 찾는 것을 좋아한다고 합니다.



- [Part 1 - 브라우저에서의 Rust](#part-1---브라우저에서의-rust)
  - [Rust Playground](#rust-playground)
  - [🚧 과 ⚠️](#-과-️)
  - [주석](#주석)
  - [Types](#types)
    - [Primitive types](#primitive-types)
  - [Type inference](#type-inference)
    - [Floats](#floats)
  - [Printing 'hello, world!'](#printing-hello-world)
    - [Declaring variables and code blocks](#declaring-variables-and-code-blocks)
  - [Display and debug](#display-and-debug)
    - [Smallest and largest numbers](#smallest-and-largest-numbers)
  - [Mutability (changing)](#mutability-changing)
    - [Shadowing](#shadowing)
  - [The stack, the heap, and pointers](#the-stack-the-heap-and-pointers)
  - [More about printing](#more-about-printing)
  - [Strings](#strings)
  - [const and static](#const-and-static)
  - [More on references](#more-on-references)
  - [Mutable references](#mutable-references)
    - [Shadowing again](#shadowing-again)
  - [Giving references to functions](#giving-references-to-functions)
  - [Copy types](#copy-types)
    - [Variables without values](#variables-without-values)
  - [Collection types](#collection-types)
    - [Arrays](#arrays)
  - [Vectors](#vectors)
  - [Tuples](#tuples)
  - [Control flow](#control-flow)
  - [Structs](#structs)
  - [Enums](#enums)
    - [Enums to use multiple types](#enums-to-use-multiple-types)
  - [Loops](#loops)
  - [Implementing structs and enums](#implementing-structs-and-enums)
  - [Destructuring](#destructuring)
  - [References and the dot operator](#references-and-the-dot-operator)
  - [Generics](#generics)
  - [Option and Result](#option-and-result)
    - [Option](#option)
    - [Result](#result)
  - [Other collections](#other-collections)
    - [HashMap (and BTreeMap)](#hashmap-and-btreemap)
    - [HashSet and BTreeSet](#hashset-and-btreeset)
    - [BinaryHeap](#binaryheap)
    - [VecDeque](#vecdeque)
  - [The ? operator](#the--operator)
    - [When panic and unwrap are good](#when-panic-and-unwrap-are-good)
  - [Traits](#traits)
    - [The From trait](#the-from-trait)
    - [Taking a String and a &str in a function](#taking-a-string-and-a-str-in-a-function)
  - [Chaining methods](#chaining-methods)
  - [Iterators](#iterators)
    - [How an iterator works](#how-an-iterator-works)
  - [Closures](#closures)
    - [|_| in a closure](#_-in-a-closure)
    - [Helpful methods for closures and iterators](#helpful-methods-for-closures-and-iterators)
  - [The dbg! macro and .inspect](#the-dbg-macro-and-inspect)
  - [Types of &str](#types-of-str)
  - [Lifetimes](#lifetimes)
  - [Interior mutability](#interior-mutability)
    - [Cell](#cell)
    - [RefCell](#refcell)
    - [Mutex](#mutex)
    - [RwLock](#rwlock)
  - [Cow](#cow)
  - [Type aliases](#type-aliases)
    - [Importing and renaming inside a function](#importing-and-renaming-inside-a-function)
  - [The todo! macro](#the-todo-macro)
  - [Rc](#rc)
  - [Multiple threads](#multiple-threads)
  - [Closures in functions](#closures-in-functions)
  - [impl Trait](#impl-trait)
  - [Arc](#arc)
  - [Channels](#channels)
  - [Reading Rust documentation](#reading-rust-documentation)
    - [assert_eq!](#assert_eq)
    - [Searching](#searching)
    - [[src] button](#src-button)
    - [Information on traits](#information-on-traits)
  - [Attributes](#attributes)
  - [Box](#box)
  - [Box around traits](#box-around-traits)
  - [Default and the builder pattern](#default-and-the-builder-pattern)
  - [Deref and DerefMut](#deref-and-derefmut)
  - [Crates and modules](#crates-and-modules)
  - [Testing](#testing)
    - [Test-driven development](#test-driven-development)
  - [External crates](#external-crates)
    - [rand](#rand)
    - [rayon](#rayon)
    - [serde](#serde)
    - [regex](#regex)
    - [chrono](#chrono)
  - [A tour of the standard library](#a-tour-of-the-standard-library)
    - [Arrays](#arrays-1)
    - [char](#char)
    - [Integers](#integers)
    - [Floats](#floats)
    - [Bool](#bool)
    - [Vec](#vec)
    - [String](#string)
    - [OsString and CString](#osstring-and-cstring)
    - [Mem](#mem)
    - [Prelude](#prelude)
    - [Time](#time)
    - [Other-macros](#other-macros)
  - [Writing macros](#writing-macros)
- [Part 2 - Rust on your computer](#part-2---rust-on-your-computer)
  - [Cargo](#cargo)
  - [Taking_user_input](#taking-user-input)
  - [Using files](#using-files)
  - [Cargo doc](#cargo-doc)
  - [The end?](#the-end?)

# Part 1 - 브라우저에서의 Rust

이 책은 두 파트로 구성되어 있습니다. Part 1에서는 브라우저에서 최대한 많은 Rust를 실습할 예정입니다. Rust를 설치하지 않고도 알아야할 거의 모든 것을 실제로 배울 수 있으므로 Part 1은 매우 깁니다. 그런 다음 마지막에 Part 2가 있습니다. 훨씬 짧고, 로컬 컴퓨터에서의 Rust에 관한 것입니다. 해당 파트에서는 브라우저 외부에서만 수행할 수 있는 필수적으로 알아야 할 다른 모든 것을 배울 수 있습니다. 몇 가지 예는 파일 작업, 사용자 입력, 그래픽스, 그리고 개인 설정 가져오기입니다. Part 1이 끝날 때쯤엔 Rust가 설치하고 싶을 정도로 좋아지길 바랍니다. 그리고 만약 그렇지 않더라도 문제 없습니다. Part 1은 당신이 신경쓰지 않을 만큼 많은 것을 가르쳐줄 것입니다.

## Rust Playground
**[이 챕터를 YouTube에서 보기](https://youtu.be/-lYeJeQ11OI)**

여러분은 아직 Rust를 설치하고 싶지 않을 수도 있다면 그래도 상관없습니다. [https://play.rust-lang.org/](https://play.rust-lang.org/)으로 이동하여 브라우저를 떠나지 않고 Rust를 작성해볼 수 있습니다. 그곳에서 코드를 작성하고 실행 버튼(Run)을 클릭하여 결과를 확인할 수 있습니다. 이 책에 있는 대부분의 샘플은 브라우저의 Playground에서 실행할 수 있습니다. 거의 끝날 무렵에서 Playground에서 할 수 있는 것을 뛰어넘는 예제(파일 열기와 같은)를 볼 수 있을 겁니다.

다음은 Rust Playground를 사용할 때의 몇가지 팁입니다:

- Run으로 코드를 실행
- 코드를 더 빠르게 하려면 Debug를 Release로 변경하세요. Debug: 컴파일 속도가 빨라지고 실행 속도가 느려지며 디버그 정보가 포함됩니다. Release: 컴파일 속도가 느려지고 실행 속도가 훨씬 빠라지며 디버그 정보가 제거됩니다.
- URL 링크를 얻으려면 Share를 클릭하세요. 도움이 필요한 경우 이를 사용하여 코드를 공유할 수 있습니다. Share를 클릭한 후 `Open a new thread in the Rust user forum`을 클릭하여 포럼에 있는 사람들에게 바로 도움을 요청할 수 있습니다.
- Tools: Rustfmt는 코드를 멋지게 포매팅해줍니다.
- Tools: Clippy는 코드를 개선하는 방법에 대한 추가 정보를 제공합니다.
- Config: 여기에서 테마를 다크 모드로 변경하여 야간 작업 및 기타 여러 구성을 할 수 있습니다.

만약 Rust를 설치하고 싶다면 [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install)로 이동하여 세부 지침을 따라하세요. 일반적으로 `rustup`을 사용하여 Rust를 설치하고 업데이트합니다.

## 🚧 과 ⚠️

간혹 책의 코드 예제가 동작하지 않을 수 있습니다. 예제가 작동하지 않으면 🚧 또는 ⚠️이 표시됩니다. 🚧는 "공사중"의 의미로 코드가 완료되지 않았음을 뜻합니다. Rust는 실행하기 위해 `fn main()`(메인함수)가 필요하지만 때로는 `fn main()`이 없는 작은 코드 조각만 보고 싶을 때가 있습니다. 그 예제들은 정확하지만 실행하려면 `fn main()`이 필요합니다. 그리고, 일부 코드 예제는 우리가 고칠 문제를 보여줍니다. 그 예제들은 `fn main()`이 있을 수 있지만 오류를 생성하므로 ⚠️가 표시됩니다.

## 주석
**[이 챕터를 YouTube에서 보기](https://youtu.be/x7GlQjh2aSw)**

주석은 컴퓨터가 아니라 프로그래머가 읽을 수 있도록 작성되는 것입니다. 다른 사람들이 코드를 이해하는 데 도움이 되도록 주석을 작성하는 것이 좋습니다. 또한 나중에 코드를 이해하는 데 도움이 됩니다. (많은 사람들이 좋은 코드를 작성하지만 왜 작성했는지 잊어버리곤 합니다.) Rust에서 주석을 작성하려면 일반적으로 `//`를 사용합니다:

```rust
fn main() {
    // Rust 프로그램은 fn main()으로 시작합니다.
    // 코드를 블록 안에 넣으세요. { 로 시작해서 } 로 끝납니다.
    let some_number = 100; // 여기에 원하는만큼 주석을 작성할 수 있으며 컴파일러는 이것을 보지 않을겁니다.
}
```

위와 같이 한다면 컴파일러는 `//`의 오른쪽에 있는 아무 것도 보지 않을겁니다.

`/*`로 시작해서 `*/`로 끝나는 다른 종류의 주석이 있습니다. 이것은 코드 중간에 작성하는데 유용한 방법입니다.

```rust
fn main() {
    let some_number/*: i16*/ = 100;
}
```

컴파일러에게 `let some_number/*: i16*/ = 100;`은 `let some_number = 100;`과 같이 보입니다.

The `/* */` form is also useful for very long comments over more than one line. In this example you can see that you need to write `//` for every line. But if you type `/*`, it won't stop until you finish it with `*/`.

`/* */` 형식은 한 줄 이상의 매우 긴 주석에도 유용합니다. 아래 예제에서 모든 줄에 `//`을 작성해야하는 것을 볼 수 있습니다. 그러나 `/*`를 입력하면 `*/`로 끝날 때까지 멈추지 않습니다.

```rust
fn main() {
    let some_number = 100; /* 이 숫자에 대해
    약간의 설명을 하겠습니다.
    나의 가장 좋아하는 숫자 100 입니다.
    some_number 라고 불리지만 사실 제 생각에는... */

    let some_number = 100; // 이 숫자에 대해
    // 약간의 설명을 하겠습니다.
    // 나의 가장 좋아하는 숫자 100 입니다.
    // some_number 라고 불리지만 사실 제 생각에는...
}
```
