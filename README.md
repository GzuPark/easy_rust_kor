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

Rust에는 **primitive types**(primitive = 매우 기본적)이라고 하는 간단한 타입이 있습니다. 우리는 우선 integer(정수)와 `char`(문자)로 시작하겠습니다. 정수는 소수점이 없는 숫자를 말합니다. 그리고 정수에는 두가지 타입이 있습니다:

- Signed integers(부호 있는 정수),
- Unsigned integers(부호 없는 정수).

Signed는 `+`(더하기 부호) 그리고 `-`(빼기 기호)를 의미하므로 부호 있는 정수는 양수 또는 음수(예: +8, -8)이 될 수 있습니다. 그러나 부호 없는 정수는 부호가 없기 때문에 양수만 가능합니다.

부호 있는 정수는 `i8`, `i16`, `i32`, `i64`, `i128`, 그리고 `isize`로 나타냅니다.
부호 없는 정수는 `u8`, `u16`, `u32`, `u64`, `u128`, 그리고 `usize`로 나타냅니다.

`i` 또는 `u` 뒤의 숫자는 해당 숫자의 비트수를 의미하므로 비트가 많을 수록 숫자가 커질 수 있습니다. 8 bits = 1 bytes 이므로 `i8`은 1 bytes, `i64`는 8 bytes 등입니다. 크기가 더 큰 숫자 타입은 더 큰 숫자를 포함할 수 있습니다. 예를 들어 `u8`은 최대 255까지 담을 수 있지만 `u16`은 65535까지 담을 수 있습니다. 그리고, `u128`은 340282366920938463463374607431768211455까지 담을 수 있습니다.

그렇다면 `isize`와 `usize`는 무엇일까요? 이것은 컴퓨터 타입의 비트수를 의미합니다. (컴퓨터의 비트수를 컴퓨터의 **아키텍처**라고 합니다.) 따라서 32 bits 컴퓨터의 `isize`와 `usize`는 `i32`와 `u32`, 그리고 64 bits 컴퓨터의 `isize`와 `usize`는 `i64` 및 `u64`와 같습니다.

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

가장 많이 사용되는 문자는 256 미만의 숫자로 `u8`에 들어갈 수 있습니다. `u8`은 0에 255까지의 모든 숫자를 더한 것이므로 총 256이 됩니다. 이것은 Rust가 `as`를 사용하여 `u8`을 `char`로 안전하게 **타입변환(cast)**할 수 있음을 의미합니다. ("`u8`을 `char`로 타입변환"은 "`u8`이 `char`인 척하는 것"을 의미합니다.)

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
