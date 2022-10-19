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
  - [타입](#타입)
    - [기본 타입](#기본-타입)
  - [타입 추론](#타입-추론)
    - [부동소수](#부동소수)
  - ['Hello, world!' 출력하기](#hello-world-출력하기)
    - [변수 선언과 코드 블럭](#변수-선언과-코드-블럭)
  - [디스플레이와 디버그](#디스플레이와-디버그)
    - [가작 작은 숫자와 가장 큰 숫자](#가작-작은-숫자와-가장-큰-숫자)
  - [Mutability (가변성)](#mutability-가변성)
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

## 타입

Rust에는 숫자, 문자 등으로 작업할 수 있는 많은 타입이 있습니다. 일부는 간단하고 다른 일부는 더 복잡하며, 그리고 직접 만드는 것도 가능합니다.

### 기본 타입
**이 챕터를 YouTube에서 보기: [Video 1](https://youtu.be/dEMYR99YIao), [Video 2](https://youtu.be/yR33X2Ik9W0), [Video 3](https://youtu.be/fpDTY7UuPaw)**

Rust에는 **primitive types** (primitive = 매우 기본적)이라고 하는 간단한 타입이 있습니다. 우리는 우선 integer(정수)와 `char`(문자)로 시작하겠습니다. 정수는 소수점이 없는 숫자를 말합니다. 그리고 정수에는 두가지 타입이 있습니다:

- Signed integers(부호 있는 정수),
- Unsigned integers(부호 없는 정수).

Signed는 `+`(더하기 부호) 그리고 `-`(빼기 기호)를 의미하므로 부호 있는 정수는 양수 또는 음수(예: +8, -8)이 될 수 있습니다. 그러나 부호 없는 정수는 부호가 없기 때문에 양수만 가능합니다.

부호 있는 정수는 `i8`, `i16`, `i32`, `i64`, `i128`, 그리고 `isize`로 나타냅니다.
부호 없는 정수는 `u8`, `u16`, `u32`, `u64`, `u128`, 그리고 `usize`로 나타냅니다.

`i` 또는 `u` 뒤의 숫자는 해당 숫자의 비트수를 의미하므로 비트가 많을 수록 숫자가 커질 수 있습니다. 8 bits = 1 bytes 이므로 `i8`은 1 bytes, `i64`는 8 bytes 등입니다. 크기가 더 큰 숫자 타입은 더 큰 숫자를 포함할 수 있습니다. 예를 들어 `u8`은 최대 255까지 담을 수 있지만 `u16`은 65535까지 담을 수 있습니다. 그리고, `u128`은 340282366920938463463374607431768211455까지 담을 수 있습니다.

그렇다면 `isize`와 `usize`는 무엇일까요? 이것은 컴퓨터 타입의 비트수를 의미합니다. (컴퓨터의 비트수를 컴퓨터의 **아키텍처** 라고 합니다.) 따라서 32 bits 컴퓨터의 `isize`와 `usize`는 `i32`와 `u32`, 그리고 64 bits 컴퓨터의 `isize`와 `usize`는 `i64` 및 `u64`와 같습니다.

다양한 타입의 정수에는 여러가지 이유가 있습니다. 한 가지 이유는 컴퓨터 성능입니다. bytes 수가 적을수록 처리 속도가 더 빠릅니다. 예를 들어 숫자 -10은 `i8`로 `11110110`이지만 `i128`로는 `11111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111110110` 입니다. 그러나 여기에는 몇 가지 다른 용도가 있습니다:

Rust에서는 문자를 `char`라고 합니다. 모든 `char`는 숫자로 표시할 수 있습니다: 문자 `A`는 숫자 65, 반면 문자 `友`(중국어로 "친구")는 숫자 21451입니다. 이 숫자 목록을 "Unicode"라고 합니다. Unicode는 A 부터 Z, 숫자 0 부터 9, 또는 공백과 같이 많이 사용되는 문자에 더 작은 숫자를 사용합니다.

```rust
fn main() {
    let first_letter = 'A';
    let space = ' '; // ' ' 안의 공백도 문자입니다.
    let other_language_char = 'Ꮔ'; // Unicode 덕분에 Cherokee와 같은 다른 언어도 잘 표시됩니다.
    let cat_face = '😺'; // 이모티콘도 문자입니다.
}
```

가장 많이 사용되는 문자는 256 미만의 숫자로 `u8`에 들어갈 수 있습니다. `u8`은 0에 255까지의 모든 숫자를 더한 것이므로 총 256이 됩니다. 이것은 Rust가 `as`를 사용하여 `u8`을 `char`로 안전하게 **타입변환(cast)** 할 수 있음을 의미합니다. ("`u8`을 `char`로 타입변환"은 "`u8`이 `char`인 척하는 것"을 의미합니다.)

`as`로 casting하는 것은 Rust가 매우 엄격하기 때문에 유용합니다. 항상 타입을 알아야하며 두 타입이 모두 정수인 경우에도 두 개의 다른 타입을 함께 사용할 수 없습니다. 예를 들어 다음은 작동하지 않습니다:

```rust
fn main() { // main()은 Rust 프로그램이 실행을 시작하는 곳입니다. 코드는 {} (중괄호) 안에 들어갑니다.

    let my_number = 100; // 우리는 정수 타입을 작성하지 않았으므로,
                         // Rust는 i32을 선택합니다. 다른 타입을
                         // 사용하도록 지시하지 않으면 Rust는 항상
                         // 정수에 대해 i32를 선택합니다.

    println!("{}", my_number as char); // ⚠️
}
```

이유는 다음과 같습니다:

```text
error[E0604]: only `u8` can be cast as `char`, not `i32`
 --> src\main.rs:3:20
  |
3 |     println!("{}", my_number as char);
  |                    ^^^^^^^^^^^^^^^^^
```

다행히 `as`를 사용하여 이 문제를 쉽게 고칠 수 있습니다. `i32`를 `char`로 타입변환 할 수 없지만 `i32`를 `u8`로 타입변환 할 수 있습니다. 그런 다음 `u8`에서 `char`까지 동일한 작업을 수행할 수 있습니다. 따라서 한줄에서 `as`를 사용하여 `my_number`를 `u8`으로 만들고 다시 `char`로 만들 수 있습니다. 이제 컴파일하면 됩니다:

```rust
fn main() {
    let my_number = 100;
    println!("{}", my_number as u8 as char);
}
```

위 예제는 100에 위치한 문자인 `d`가 출력됩니다.

그러나 더 쉬운 방법은 Rust에게 `my_number`가 `u8`이라고 알려주는 것입니다. 그 방법은 다음과 같습니다:

```rust
fn main() {
    let my_number: u8 = 100; // my_number 를 my_number: u8 로 수정합니다.
    println!("{}", my_number as char);
}
```

이것이 Rust에서 모든 다른 숫자 타입에 대한 두 가지 이유입니다. 또 다른 이유로는 `usize`는 Rust가 *인덱싱*에 사용하는 크기입니다. (인덱싱은 "어떤 항목이 첫번째인지", "어떤 항목이 두번째인지" 등을 의미합니다.) `usize`는 다음과 같은 이유로 인덱싱에 가장 적합한 크기입니다.

- 인덱스는 음수일 수 없으므로 `u`가 있는 숫자여야 합니다.
- 때로 많은 것을 인덱싱해야 하기 때문에 커야합니다. 하지만,
- 32 bits 컴퓨터는 `u64`를 사용할 수 없기 때문에 `u64`가 될 수 없습니다.

따라서 Rust는 `usize`를 사용하여 컴퓨터가 읽을 수 있는 가장 큰 인덱싱 숫자를 얻을 수 있습니다.


자 그럼 `char`에 대해 좀 배워볼 차례입니다. `char`는 항상 하나의 문자이고 `""` 대신 `''`를 사용합니다.

모든 `chars`는 4 bytes의 메모리를 사용합니다. 4 bytes는 모든 종류의 문자를 담기에 충분하기 때문입니다:
- 기본 문자와 기호는 일반적으로 4 bytes 중 1 byte가 필요합니다: `a b 1 2 + - = $ @`
- 독일어 움라우트나 악센트와 같은 다른 문자는 4 bytes 중 2 bytes가 필요합니다: `ä ö ü ß è é à ñ`
- 한국어, 일본어, 또는 한자는 3 bytes 또는 4 bytes가 필요합니다: `国 안 녕`

문자를 문자열의 일부로 사용할 때 문자열은 각 문자에 필요한 최소 메모리 양을 사용하도록 인코딩됩니다.

우리는 `.len()`을 사용하여 다음과 같이 직접 확인해볼 수 있습니다:

```rust
fn main() {
    println!("Size of a char: {}", std::mem::size_of::<char>()); // 4 bytes
    println!("Size of string containing 'a': {}", "a".len()); // .len()은 문자열의 크기를 bytes 단위로 보여줍니다.
    println!("Size of string containing 'ß': {}", "ß".len());
    println!("Size of string containing '国': {}", "国".len());
    println!("Size of string containing '𓅱': {}", "𓅱".len());
}
```

위 예제는 아래와 같이 출력됩니다:

```text
Size of a char: 4
Size of string containing 'a': 1
Size of string containing 'ß': 2
Size of string containing '国': 3
Size of string containing '𓅱': 4
```

`a`는 1 byte, 독일어인 `ß`는 2 bytes, 일본어인 `国`는 3 bytes, 그리고 고대 이집트 상형문자인 `𓅱`는 4 bytes라는 것을 확인할 수 있습니다.

```rust
fn main() {
    let slice = "Hello!";
    println!("Slice is {} bytes.", slice.len());
    let slice2 = "안녕!";
    println!("Slice2 is {} bytes.", slice2.len());
}
```

위 예제는 아래와 같이 출력됩니다:

```text
Slice is 6 bytes.
Slice2 is 7 bytes.
```

`slice`는 길이가 6글자 그리고 6 bytes지만, `slice2`는 길이가 3글자 그리고 7 bytes입니다.

만약 `.len()`이 크기를 byte 단위로 제공하는 경우 문자 크기는 어떻게 될까요? 우리는 이 메소드들에 대해 나중에 배우겠지만 `.chars().count()`가 이 작업을 할 수 있다는 것을 기억하면 좋겠습니다. `.chars().count()`는 작성한 내용을 문자로 변환한 다음 문자의 개수를 세는 과정을 거칩니다.


```rust
fn main() {
    let slice = "Hello!";
    println!("Slice is {} bytes and also {} characters.", slice.len(), slice.chars().count());
    let slice2 = "안녕!";
    println!("Slice2 is {} bytes but only {} characters.", slice2.len(), slice2.chars().count());
}
```

위 예제는 아래와 같이 출력됩니다:

```text
Slice is 6 bytes and also 6 characters.
Slice2 is 7 bytes but only 3 characters.
```

## 타입 추론
**[이 챕터를 YouTube에서 보기](https://youtu.be/qHEFgX-zCSs)**

타입 추론은 컴파일러에게 타입을 알려주지 않지만 컴파일러가 스스로 결정할 수 있다면 결정하는 것을 의미합니다. 컴파일러는 항상 변수의 타입을 알아야 하지만 그렇다고 항상 선언해줄 필요는 없습니다. 사실 일반적으로 선언할 필요가 없습니다. 예를 들어 `let my_number = 8`의 경우 `my_number`는 `i32`가 됩니다. 컴파일러가 알려주지 않으면 정수로 `i32`를 선택하기 때문입니다. 그러나 `let my_number: u8 = 8`이라고 말하면 `my_number`를 `u8`으로 지정했기 때문에 `u8`이 됩니다.

따라서 일반적으로 컴파일러는 추측을 할 수 있습니다. 그러나 때로는 다음 두 가지 이유로 알려줘야만 합니다:

1) 작업이 매우 복잡하기 때문에 컴파일러는 원하는 타입을 알 수 없습니다.
2) 다른 타입을 원합니다.(예를 들면, `i32`가 아닌 `i128`)

타입을 명시하려면 변수 이름 뒤에 콜론(`:`)을 추가합니다.

```rust
fn main() {
    let small_number: u8 = 10;
}
```

숫자의 경우 숫자 뒤에 타입을 말할 수 있습니다. 공백이 필요하지는 않고, 그냥 숫자 바로 뒤에 입력하면 됩니다.

```rust
fn main() {
    let small_number = 10u8; // 10u8 = u8 타입의 10
}
```

숫자를 읽기 쉽게 만들고 싶다면 `_`를 추가할 수도 있습니다.

```rust
fn main() {
    let small_number = 10_u8; // 이것은 더 읽기 쉽습니다.
    let big_number = 100_000_000_i32; // 1억이라는 숫자는 _ 을 사용하여 읽기 쉽게 됩니다.
}
```

`_`는 숫자를 변경하지 않습니다. 단지 읽기 쉽게 하기 위한 것입니다. 그리고 얼마나 많은 `_`를 사용하는지는 중요하지 않습니다:

```rust
fn main() {
    let number = 0________u8;
    let number2 = 1___6______2____4______i32;
    println!("{}, {}", number, number2);
}
```

위 예제는 `0, 1624`로 출력됩니다.

### 부동소수

부동소수(Float)은 소수점이 있는 숫자입니다. 5.5는 부동소수이고, 6은 정수입니다. 5.0도 부동소수이고 5.도 부동소수입니다.

```rust
fn main() {
    let my_float = 5.; // Rust는 .를 보고 부동소수임을 알 수 있습니다.
}
```

그러나 타입을 `float`이라고 하지 않고, `f32` 그리고 `f64`로 표시합니다. 정수와 동일합니다: `f` 뒤의 숫자는 bits 수를 나타냅니다. 타입을 작성하지 않으면 Rust는 `f64`를 선택합니다.

물론 같은 타입의 부동소수만 함께 사용할 수 있습니다. 따라서 `f64`에 `f32`를 더하는 것은 할 수 없습니다.

```rust
fn main() {
    let my_float: f64 = 5.0; // 이것은 f64 입니다.
    let my_other_float: f32 = 8.5; // 이것은 f32 입니다.

    let third_float = my_float + my_other_float; // ⚠️
}
```

위 예제를 실행하려고 하면, Rust는 아래와 같이 말할 것입니다:

```text
error[E0308]: mismatched types
 --> src\main.rs:5:34
  |
5 |     let third_float = my_float + my_other_float;
  |                                  ^^^^^^^^^^^^^^ expected `f64`, found `f32`
```

컴파일러는 잘못된 타입을 사용할 때 "expected (타입), found (타입)"을 씁니다. 다음과 같이 코드를 읽습니다:

```rust
fn main() {
    let my_float: f64 = 5.0; // 컴파일러는 f64를 봅니다.
    let my_other_float: f32 = 8.5; // 컴파일러는 f32를 봅니다. 다른 타입 입니다.
    let third_float = my_float + // my_float에 무언가 더하길 원하므로 f64에 다른 f64를 사용해야 합니다. 이제 f64를 기대합니다...
    let third_float = my_float + my_other_float;  // ⚠️ 그러나 f32를 발견했고, 더하기를 할 수 없습니다.
}
```

따라서 "expected (타입), found (타입)"이 표시되면 컴파일러가 다른 타입을 예상한 이유를 찾아야 합니다.

물론 간단한 숫자로 쉽게 고칠 수 있습니다. `as`를 사용하여 `f32`를 `f64`로 캐스팅할 수 있습니다.

```rust
fn main() {
    let my_float: f64 = 5.0;
    let my_other_float: f32 = 8.5;

    let third_float = my_float + my_other_float as f64; // my_other_float as f64 와 같이 my_other_float 를 f64처럼 사용합니다.
}
```

또는 더 간단하게 타입 선언을 제거합니다. ("타입 선언" = "Rust에게 해당 타입을 사용하도록 지시") Rust는 함께 덧셈을 할 수 있는 타입을 선택합니다.

```rust
fn main() {
    let my_float = 5.0; // Rust는 f64를 선택합니다.
    let my_other_float = 8.5; // 여기서 다시 f64를 선택합니다.

    let third_float = my_float + my_other_float;
}
```

Rust 컴파일러는 똑똑하고 f32가 필요한 경우 f64를 선택하지 않습니다:

```rust
fn main() {
    let my_float: f32 = 5.0;
    let my_other_float = 8.5; // Rust는 보통 f64를 선택합니다만,

    let third_float = my_float + my_other_float; // 이제 f32에 덧셈을 수행해야한다는 것을 알고 있습니다. 따라서 my_other_float에도 f32를 선택합니다.
}
```

## 'Hello, world!' 출력하기
**이 챕터를 YouTube에서 보기: [Video 1](https://youtu.be/jpLwve-7Cjg), [Video 2](https://youtu.be/f-UCvEs7J3I)**

새로운 Rust 프로그램을 시작하면 항상 아래의 코드를 확인할 수 있습니다:

```rust
fn main() {
    println!("Hello, world!");
}
```

- `fn`는 함수를 의미하고,
- `main`은 프로그램의 시작을 알리는 함수이며,
- `()`는 함수에 시작할 변수를 지정하지 않았음을 의미합니다.

`{}`는 **코드 블럭** 이라고 합니다. 이것은 코드가 있는 공간입니다.

`println!`은 콘솔에 출력하는 **매크로** 입니다. **매크로** 는 코드를 작성하는 함수와 비슷합니다. 매크로 뒤에는 `!`이 있습니다. 나중에 매크로를 작성하는 방법에 배울 것이고, 지금은 일단 `!`가 매크로라는 것을 기억하세요.

`;`에 대해 배우기 위해 다른 함수를 만들 것입니다. 먼저 `main`에서 숫자 8을 인쇄합니다:

```rust
fn main() {
    println!("Hello, world number {}!", 8);
}
```

`println!`의 `{}`는 "여기에 변수를 넣으세요."를 의미합니다. 따라서 위 코드는 `Hello, world number 8!`을 출력합니다.


또한 이전에 한 것처럼 더 많은 변수를 넣을 수 있습니다:

```rust
fn main() {
    println!("Hello, worlds number {} and {}!", 8, 9);
}
```

위 결과는 `Hello, worlds number 8 and 9!`을 출력합니다.

자 이제 함수를 생성해봅시다.

```rust
fn number() -> i32 {
    8
}

fn main() {
    println!("Hello, world number {}!", number());
}
```

위 결과는 마찬가지로 `Hello, world number 8!`을 출력합니다. Rust가 `number()`를 볼 때 함수를 바라봅니다. 이 함수는:

- 아무 인자도 받지 않습니다. (왜냐하면 `()` 때문입니다.)
- `i32` 타입으로 반환합니다. `->` (얇은 화살표)는 함수가 반환하는 타입을 보여줍니다.

함수 내부에는 단지 `8`만 있습니다. `;`이 없기 때문에 그 값 자체를 반환하게 됩니다. 만약 `;`가 있다면 아무 것도 반환하지 않습니다 (`()`를 반환합니다). 반환 타입이 `i32`를 반환하고 `;`는 `i32`가 아닌 `()`를 반환하기 때문에 Rust는 `;`가 있을 경우 함수를 컴파일하지 않습니다:

```rust
fn main() {
    println!("Hello, world number {}", number());
}

fn number() -> i32 {
    8;  // ⚠️
}
```

```text
5 | fn number() -> i32 {
  |    ------      ^^^ expected `i32`, found `()`
  |    |
  |    implicitly returns `()` as its body has no tail or `return` expression
6 |     8;
  |      - help: consider removing this semicolon
```

위 결과는 "`number()`가 `i32` 타입을 반환한다고 말했지만 아무것도 반환하지 않도록 `;`가 추가됐습니다"를 알려줍니다. 따라서 컴파일러는 세미콜론을 제거할 것을 제안하고 있습니다.

`return 8;`이라고 작성할 수도 있지만 Rust에서는 일반적으로 `;`과 `return`을 제거합니다.

함수에 변수를 주고 싶을 때는 `()` 안에 변수를 넣어주면 됩니다. 변수의 이름과 타입에 대해 명시해줘야 합니다.

```rust
fn multiply(number_one: i32, number_two: i32) { // 두 개의 i32가 함수의 인자로 사용됩니다. 각 인자를 number_one과 number_two라고 부르고 있습니다.
    let result = number_one * number_two;
    println!("{} times {} is {}", number_one, number_two, result);
}

fn main() {
    multiply(8, 9); // 숫자를 직접 적어줄 수 있습니다.
    let some_number = 10; // 또는 두 개의 변수를 선언하여
    let some_other_number = 2;
    multiply(some_number, some_other_number); // 함수 안에 넣어줄 수도 있습니다.
}
```

또한 `i32` 타입을 반환할 수 있습니다. 단지 마지막의 세미콜론을 제거해주세요:

```rust
fn multiply(number_one: i32, number_two: i32) -> i32 {
    let result = number_one * number_two;
    println!("{} times {} is {}", number_one, number_two, result);
    result // 이것이 반환되는 i32 타입입니다.
}

fn main() {
    let multiply_result = multiply(8, 9); // multiply()를 사용하여 출력하고, 결과를 multiply_result 변수에 전달합니다.
}
```

### 변수 선언과 코드 블럭

변수를 선언하기 위해서는 `let`을 사용하면 됩니다. (변수를 선언한다 = Rust에게 변수를 만들 것을 이야기해준다)

```rust
fn main() {
    let my_number = 8;
    println!("Hello, number {}", my_number);
}
```

변수는 코드 블럭 `{}` 안에서 시작하고 끝납니다. 아래 예에서는 `my_number`는 자체 코드 블럭 안에 있기 때문에 `println!`을 호출하기 전에 끝납니다.

```rust
fn main() {
    {
        let my_number = 8; // my_number starts here
                           // my_number ends here!
    }

    println!("Hello, number {}", my_number); // ⚠️ my_number가 없고
                                             // println!()이 변수를 찾을 수 없습니다.
}
```

코드 블럭을 사용하여 값을 반환할 수 있습니다:

```rust
fn main() {
    let my_number = {
    let second_number = 8;
        second_number + 9 // 세미콜론이 없으므로 코드 블럭은 8 + 9를 반환합니다.
                          // 함수처럼 동작합니다.
    };

    println!("My number is: {}", my_number);
}
```

만약 블록 안에 세미콜론을 추가하면, `()`을 반환합니다(아무것도 반환하지 않음):

```rust
fn main() {
    let my_number = {
    let second_number = 8; // second_number를 선언하고,
        second_number + 9; // 9를 second_number에 더하지만
                           // 반환하지 않습니다!
                           // second_number는 여기에서 종료됩니다.
    };

    println!("My number is: {:?}", my_number); // my_number는 ()입니다.
}
```

그렇다면 왜 `{}`가 아닌 `{:?}`를 사용했을까요? 다음 챕터에서 그것에 대해 이야기할 예정입니다.

## 디스플레이와 디버그
**[See this chapter on YouTube](https://youtu.be/jd3pC248c0o)**

Rust의 간단한 변수는 `println!` 내부의 `{}`를 사용하여 출력할 수 있습니다. 그러나 일부 변수는 할 수 없고, 이를 위해서는 **디버그 출력** 이 필요합니다. 디버그 출력은 일반적으로 프로그래머에게 더 많은 정보를 보여주기 위해 사용됩니다. 디버그는 도움이 되는 추가 정보를 출력하기 때문에 보기에 좋지 않을 수도 있습니다.

`{}`가 아니라 `{:?}`가 필요한지 어떻게 알 수 있을까요? 컴파일러가 아래 예제와 같이 알려줍니다:

```rust
fn main() {
    let doesnt_print = ();
    println!("This will not print: {}", doesnt_print); // ⚠️
}
```

위 코드를 실행시키면 컴파일러는 아래와 같이 알려줍니다:

```text
error[E0277]: `()` doesn't implement `std::fmt::Display`
 --> src\main.rs:3:41
  |
3 |     println!("This will not print: {}", doesnt_print);
  |                                         ^^^^^^^^^^^^ `()` cannot be formatted with the default formatter
  |
  = help: the trait `std::fmt::Display` is not implemented for `()`
  = note: in format strings you may be able to use `{:?}` (or {:#?} for pretty-print) instead
  = note: required by `std::fmt::Display::fmt`
  = note: this error originates in a macro (in Nightly builds, run with -Z macro-backtrace for more info)
```

위 결과는 많은 정보를 보여주고 있습니다. 그러나 중요한 부분은 `you may be able to use {:?} (or {:#?} for pretty-print) instead`입니다. 이는 `{:?}` 또는 `{:#?}`을 시도할 수 있다는 의미이고, 여기서 `{:#?}`는 "정돈된 출력(pretty printing)"이라고 불립니다. `{:?}`와 비슷하지만 더 많은 행에 걸쳐 다른 형식으로 출력됩니다.

따라서 디스플레이(Display)는 `{}`로 출력하는 것을 의미하고 디버그(Debug)는 `{:?}`로 출력하는 것을 의미합니다.

한 가지 더 말하자면, 줄 바꿈을 원하지 않을 때엔 `ln` 없이 `print!`를 사용할 수 있습니다.

```rust
fn main() {
    print!("This will not print a new line");
    println!(" so this will be on the same line");
}
```

위 예제는 `This will not print a new line so this will be on the same line`를 출력합니다.

### 가작 작은 숫자와 가장 큰 숫자

만약 가장 작은 숫자와 가장 큰 숫자를 보려면, 타입 이름 뒤에 MIN 과 MAX 를 사용하면 됩니다:

```rust
fn main() {
    println!("The smallest i8 is {} and the biggest i8 is {}.", i8::MIN, i8::MAX); // 힌트: std::i8::MIN 출력은 "표준 라이브러리의 i8 섹션 내부의 MIN을 출력한다"라는 것을 의미합니다.
    println!("The smallest u8 is {} and the biggest u8 is {}.", u8::MIN, u8::MAX);
    println!("The smallest i16 is {} and the biggest i16 is {}.", i16::MIN, i16::MAX);
    println!("The smallest u16 is {} and the biggest u16 is {}.", u16::MIN, u16::MAX);
    println!("The smallest i32 is {} and the biggest i32 is {}.", i32::MIN, i32::MAX);
    println!("The smallest u32 is {} and the biggest u32 is {}.", u32::MIN, u32::MAX);
    println!("The smallest i64 is {} and the biggest i64 is {}.", i64::MIN, i64::MAX);
    println!("The smallest u64 is {} and the biggest u64 is {}.", u64::MIN, u64::MAX);
    println!("The smallest i128 is {} and the biggest i128 is {}.", i128::MIN, i128::MAX);
    println!("The smallest u128 is {} and the biggest u128 is {}.", u128::MIN, u128::MAX);

}
```

위 예제는 아래와 같이 출력됩니다:

```text
The smallest i8 is -128 and the biggest i8 is 127.
The smallest u8 is 0 and the biggest u8 is 255.
The smallest i16 is -32768 and the biggest i16 is 32767.
The smallest u16 is 0 and the biggest u16 is 65535.
The smallest i32 is -2147483648 and the biggest i32 is 2147483647.
The smallest u32 is 0 and the biggest u32 is 4294967295.
The smallest i64 is -9223372036854775808 and the biggest i64 is 9223372036854775807.
The smallest u64 is 0 and the biggest u64 is 18446744073709551615.
The smallest i128 is -170141183460469231731687303715884105728 and the biggest i128 is 170141183460469231731687303715884105727.
The smallest u128 is 0 and the biggest u128 is 340282366920938463463374607431768211455.
```

## Mutability (가변성)
**[See this chapter on YouTube](https://youtu.be/Nyyd6qn7dZY)**

`let`으로 변수를 선언할 경우 그 변수는 불변성을 가집니다 (수정할 수 없습니다).

아래 예제는 정상 동작하지 않습니다:

```rust
fn main() {
    let my_number = 8;
    my_number = 10; // ⚠️
}
```

컴파일러는 `error[E0384]: cannot assign twice to immutable variable my_number`라고 말해줄 것입니다. 이 오류는 `let`을 사용하게 되면 변수는 불변성을 가지기 때문입니다.

그러나 변수를 변경하고 싶을 때가 있습니다. 변경할 수 있는 변수를 만들기 위해서는 `let` 다음에 `mut`를 추가해주세요:

```rust
fn main() {
    let mut my_number = 8;
    my_number = 10;
}
```

위 예제는 문제가 없습니다.

그렇지만 타입을 변경할 수 없습니다: 심지어 `mut`도 할 수 없습니다. 아래 예제는 동작하지 않습니다:

```rust
fn main() {
    let mut my_variable = 8; // 변수 타입은 i32 입니다. 이는 변경되지 않습니다.
    my_variable = "Hello, world!"; // ⚠️
}
```

컴파일러를 통해 "expected" 라는 문구를 볼 수 있을 겁니다: `expected integer, found &str`. `&str`은 곧 배우게 될 문자열 타입을 말합니다.

### Shadowing
**[See this chapter on YouTube](https://youtu.be/InULHyRGw7g)**

Shadowing은 `let`을 사용하여 다른 변수와 이름이 같은 새 변수를 선언하는 것을 의미합니다. Mutability처럼 보이지만 완전히 다릅니다. Shadowing을 다음과 같습니다:

```rust
fn main() {
    let my_number = 8; // 변수 타입은 i32 입니다.
    println!("{}", my_number); // 8 을 출력합니다.
    let my_number = 9.2; // 같은 변수 이름이지만 f64 타입 입니다. 이는 첫 번째 my_number가 아닙니다(완전히 다른 것입니다)!
    println!("{}", my_number) // 9.2 를 출력합니다.
}
```

여기서 우리는 새로운 "let binding" 과 함께 `my_number`를 "shadowed" 했다고 말합니다.

그래서 첫 번째 `my_number`는 파괴됐을까요? 아닙니다, 그러나 `my_number`를 호출하면 `my_number`는 `f64` 타입을 가지게 됩니다. 그리고 동일한 블럭 범위(동일한 `{}`)에 있기 때문에 더 이상 첫 번째 `my_number`를 볼 수 없습니다.

그러나 만약 다른 블럭에 있다면 둘 다 확인할 수 있습니다. 예를 들면:

```rust
fn main() {
    let my_number = 8; // 변수 타입은 i32 입니다.
    println!("{}", my_number); // 8 을 출력합니다.
    {
        let my_number = 9.2; // 변수 타입은 f64 입니다. 이전의 my_number가 아닙니다(완전히 다른 것입니다)!
        println!("{}", my_number) // 9.2 를 출력합니다.
                                  // 그러나 shadowed my_number는 여기까지만 살아있습니다.
                                  // 첫번째 my_number 도 여전히 살아있습니다!
    }
    println!("{}", my_number); // 8 을 출력합니다.
}
```

따라서 변수를 shadowing 할 때 변수를 파괴하지 않습니다. 단지 이전 변수를 **차단** 하게 됩니다.

그렇다면 shadowing을 장점은 무엇일까요? Shadowing은 변수를 많이 변경해야 할 때 유용합니다. 변수를 사용해서 많은 간단한 수학 연산을 수행하고 싶다는 상상을 해보세요:

```rust
fn times_two(number: i32) -> i32 {
    number * 2
}

fn main() {
    let final_number = {
        let y = 10;
        let x = 9; // x 는 9로 시작합니다.
        let x = times_two(x); // shadow 된 새로운 x: 18
        let x = x + y; // shadow 된 새로운 x: 28
        x // x 반환: final_number 는 이제 x 값을 가지게 됩니다.
    };
    println!("The number is now: {}", final_number)
}
```

Shadowing이 없으면 x에 대해 신경쓰지 않으려해도 다른 이름을 생각해야 합니다:

```rust
fn times_two(number: i32) -> i32 {
    number * 2
}

fn main() {
    // Shadowing 없이 Rust를 사용하는 척합니다.
    let final_number = {
        let y = 10;
        let x = 9; // x 는 9로 시작합니다.
        let x_twice = times_two(x); // x 를 위한 두번째 변수명입니다.
        let x_twice_and_y = x_twice + y; // x 를 위한 세번째 변수명입니다!
        x_twice_and_y // Shadowing이 없어서 너무 나쁩니다. x 를 사용할 수 있었을텐데요.
    };
    println!("The number is now: {}", final_number)
}
```

일반적으로 Rust는 shadowing을 볼 수 있습니다. 빠르게 변수를 가져와서 무언가를 수행하고 다른 작업을 다시 수행할 경우에 일어납니다. 그리고, 보통은 그다지 신경쓰지 않는 빠른 변수에 사용합니다.
