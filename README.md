![Bibim logo](https://github.com/bibim-lang/bibim-lang.github.io/raw/master/logo.png)

# 비빔(Bibim) - 국수 한 그릇으로 완성되는 프로그래밍 언어
비빔은 여러분의 두뇌를 즐겁게 만들어 줄 새로운 프로그래밍 언어입니다. 기존에 사용했던 많은 프로그래밍 언어의 단점을 보완하고, 더 좋은 코드를 작성할 수 있도록 도와주는 좋은 친구이기도 합니다.

## 비빔의 장점
- 오차 없는 유리수 계산

    [부동소수점](https://ko.wikipedia.org/wiki/%EB%B6%80%EB%8F%99%EC%86%8C%EC%88%98%EC%A0%90)? 그게 뭐죠? 먹는건가요?

    비빔에서는 유리수를 손실 없이 다룹니다.

    1/1000을 1000번 더하면 정확히 1이 되어야 합니다.

- 느긋한 오류 처리

    비빔은 정말로 중요한 문제가 일어나지 않는 이상 오류를 발생시키면서 프로그램을 종료하지 않습니다.

    이는 [예외 처리를 하지 못하면 안달복달하는 어떤 섬](https://ko.wikipedia.org/wiki/%EC%9E%90%EC%99%80_%EC%84%AC)에 비해 아주 편안합니다.

- 아주 손쉬운 시분할 처리

    비빔의 코드는 순차적으로 실행되지 않습니다.

    이는 당신이 원하는대로 코드의 이곳 저곳을 누비며 실행되는 프로그램을 작성할 때에 큰 도움이 됩니다.

- 들여쓰기를 강제하지 않음

    [어떤 큰 뱀](https://ko.wikipedia.org/wiki/%ED%94%BC%ED%86%A4)과는 달리, 비빔은 사용자에게 들여쓰기를 강제하지 않습니다.

    사실, 더 정확히는 코드 내부의 공백 문자를 모두 무시합니다.

    따라서 비빔을 사용하면 여러분이 원하는 어떠한 형태로도 코드를 작성할 수 있습니다.

    만약 당신이 코드로 예술 작품을 만들고 싶으시다면 지금 바로 비빔을 사용하세요!

- 유니코드(UTF-8) 사용

    비빔은 기본적으로 소스코드와 입출력 모두 UTF-8을 사용합니다.

    [미국정보교환표준부호](https://ko.wikipedia.org/wiki/%EB%AF%B8%EA%B5%AD%EC%A0%95%EB%B3%B4%EA%B5%90%ED%99%98%ED%91%9C%EC%A4%80%EB%B6%80%ED%98%B8)는 이제 그만 놓아줍시다.

## Hello world
새로운 프로그래밍 언어를 만나면 문법은 몰라도 Hello world 코드는 꼭 봐야죠. 아래에 비빔으로 작성된 Hello world 코드가 있습니다.

```
{
    [0; @:1 = {
        [0; 72]
        [1; 69]
        [2; 76]
        [3; 76]
        [4; 79]
        [5; 32]
        [6; 87]
        [7; 79]
        [8; 82]
        [9; 76]
        [10; 68]
        [11; 10]
    }]
}
```

## 사용하기
비빔을 사용하고 싶으시다구요? Rust로 작성된 구현체인 [RustBibim](https://github.com/bibim-lang/rustbibim)로 빠르게 시작하세요.

설치하기 귀찮으시다면 [RustBibim Web Demo](https://rustbibim.update.sh/)를 통해 웹 브라우저에서 바로 사용해보세요.

## 도보시오
- 비빔을 처음 접해보신다면 [튜토리얼](https://github.com/bibim-lang/bibim-lang.github.io/blob/master/tutorial.md)을 읽어보세요.
- 비빔의 문법을 더 자세히 알고싶다면 [문법](https://github.com/bibim-lang/bibim-lang.github.io/blob/master/grammars.md)을 읽어보세요.
- 비빔으로 작성한 프로그램들의 예제를 보고 싶다면 [예제](https://github.com/bibim-lang/bibim-lang.github.io/blob/master/examples.md)를 읽어보세요.
