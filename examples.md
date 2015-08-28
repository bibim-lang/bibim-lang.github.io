# 예제
## Hello world
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

## echo
    {
        [0; @:1 = @:1]
    }
    

## fizzbuzz(주석)
    {
        [1/2; @:1/11 = { ~# fizz 문자열 #~
            [0; 102]
            [1; 105]
            [2; 122]
            [3; 122]
        }]
        [2/3; @:2/11 = { ~# buzz 문자열 #~
            [0; 98]
            [1; 117]
            [2; 122]
            [3; 122]
        }]
        [3/4; @:2 = 1] ~# 시작할 함수 위치 지정 #~
        [4/5; @:3/11 = 1] ~# 1부터 100까지 증가할 수 초기화 #~
        [@:2 + 0; @:2/7 = @:3/11] ~# 함수 @:1/3을 호출하기 위해 출력할 정수 대입 #~
        [@:2 + 1; @:3/7 = 3] ~# 함수 @:1/3을 호출 후 이동할 위치 3 대입 #~
        [@:2 + 2; @:1/3 = @:0 + 1] ~# 함수 @:1/3을 호출 #~
        [@:3 + 0; @:1 = @:6/7] ~# 함수 @:1/3의 결과로 얻은 변환된 정수 문자열 출력 #~
        [@:3 + 1; @:1 = { ~# ': ' 출력 #~
            [0; 58]
            [1; 32]
        }]
        [@:3 + 2; {
            [1; @:1 = @:1/11]
        }:(^((@:3/11)/3) ?= 1)] ~# 3의 배수인 경우 fizz 출력 #~
        [@:3 + 4; {
            [1; @:1 = @:2/11]
        }:(^((@:3/11)/5) ?= 1)] ~# 5의 배수인 경우 buzz 출력 #~
        [@:3 + 5; @:3/11 = @:3/11 + 1] ~# @:3/11를 1 증가시킴 #~
        [@:3 + 6; @:1 = {
            [0; 10]
        }] ~# 개행 #~
        [@:3 + 7; {
            [1; @:2 = @:0 + 1]
        }:(@:3/11 < 101)] ~# 아직 100까지 출력하지 않았다면 @:2로 되돌아감 #~
    
        ~# 함수: @:1/2 = 정수의 길이를 반환 #~
        ~# 입력: @:2/5 = 확인할 정수, @:3/5 = 함수 종료 후 이동할 위치 #~
        ~# 출력: @:4/5 = 확인한 정수의 길이 #~
        [@:1/2; @:1/5 = @:0 + 3]
        [@:1/5 - 2; @:4/5 = 0] ~# 출력 결과에 0을 대입 #~
        [@:1/5 - 1; @:(0 - 1)/5 = @:2/5] ~# @:(0 - 1)/5 = 확인할 변수를 담은 임시 변수 #~
        [@:1/5 + 0; @:4/5 = @:4/5 + 1] ~# 출력 결과를 1 증가 #~
        [@:1/5 + 2; @:(0 - 1)/5 = (@:(0 - 1)/5) / 10] ~# @:(0 - 1)/5 를 10으로 나누어 다시 저장 #~
        [@:1/5 + 3; { ~# @:(0 - 1)/5 가 1보다 크거나 같으면 @:1/5로 되돌아감 #~
            [1; @:1/5 = @:0 + 1]
        }:!(@:(0 - 1)/5 < 1)]
        [@:1/5 + 4; @:(@:3/5) = @:0 + 1] ~# 함수 탈출 #~
    
        ~# 함수: @:1/3 = 정수를 자릿수별로 나눠서 ascii로 변환한 Bowl으로 반환 #~
        ~# 입력: @:2/7 = 변환할 정수, @:3/7 = 함수 종료 후 이동할 위치 #~
        ~# 출력: @:6/7 = 변환된 Bowl #~
        [@:1/3; @:1/7 = @:0 + 1]
        [@:1/7 + 0; @:6/7 = {}] ~# 변환 결과를 저장할 Bowl 초기화 #~
        [@:1/7 + 1; @:(0 - 1)/7 = @:2/7] ~# 변환할 정수 임시 변수 @:(0 - 1)/7 에 복사 #~
        [@:1/7 + 2; @:2/5 = @:2/7] ~# 함수 @:1/2를 호출하기 위해 확인할 정수 대입 #~
        [@:1/7 + 3; @:3/5 = 1/13] ~# 함수 @:1/2를 호출 후 이동할 위치 1/13 지정 #~
        [@:1/7 + 4; @:1/2 = @:0 + 1] ~# 함수 @:1/2를 호출 #~
        [@:1/13 + 0; @:(0 - 2)/7 = @:4/5] ~# 함수 @:1/2 호출 결과(정수의 길이)를 임시 변수 @:(0 - 2)/7 에 저장 #~
        [@:1/13 + 1; @:(0 - 3)/7 = 0] ~# 자리수 확인용 변수 @:(0 - 3)/7 초기화 #~
        [@:1/13 + 2; { ~# 정수의 길이가 0이면 함수 종료 #~
            [0; @:1/17 = @:0 + 1] ~# 정수의 길이가 0이 아니므로 계속 실행 #~
            [1; @:(@:3/7) = @:0 + 1] ~# 정수의 길이가 0이므로 함수 종료 #~
        }:(@:(0 - 2)/7 ?= 0)]
        [@:1/17 + 0; @:(0 - 4)/7 = (@:(0 - 1)/7 - @:(0 - 3)/7)/10] ~# @:(0 - 4)/7 = (임시변수 1 - 임시변수 3) / 10 #~
        [@:1/17 + 1; { ~# @:(0 - 4)/7 의 분모가 1인 경우 @:(0 - 3)/7이 현재 마지막 자리의 자릿값임#~
            [0; @:1/19 = @:0 + 1] ~# @:(0 - 3)/7 를 1 증가시켜서 다시 확인하는 코드로 이동 #~
            [1; @:1/23 = @:0 + 1] ~# @:(0 - 3)/7 를 반환할 Bowl에 추가하는 코드로 이동 #~
        }:(^(@:(0 - 4)/7) ?= 1)]
        [@:1/19 + 0; @:(0 - 3)/7 = @:(0 - 3)/7 + 1] ~# @:(0 - 3)/7 를 1 증가시킴 #~
        [@:1/19 + 1; @:1/13 = @:0 - 1] ~# @:1/13 + 2 로 이동 #~
        [@:1/23 + 0; @:(0 - 2)/7 = @:(0 - 2)/7 - 1] ~# @:(0 - 2)/7 (정수의 길이)를 1 감소시킴 #~
        [@:1/23 + 1; (@:6/7):(@:(0 - 2)/7) = @:(0 - 3)/7 + 48] ~# 반환할 Bowl의 (정수의 길이)번째에 현재 자리값을 대입 #~
        [@:1/23 + 2; @:(0 - 1)/7 = @:(0 - 4)/7] ~# @:(0 - 1)/7 의 마지막 자리수를 제거하여 대입 #~
        [@:1/23 + 3; @:1/13 = @:0 - 0] ~# @:1/13 + 1 로 이동 (자리값 초기화 수행하는 자리로) #~
    }
    
## fizzbuzz(AA)

    { [ 1 / 2 ; @ : 1 / 1 1 = { [ 0 ; 1 0 2 ] [ 1 ; 1 0 5 ] [ 2 ; 1 2 2 ]
     [ 3 ; 1 2 2 ] } ] [ 2 / 3 ; @ : 2 / 1 1 = { [ 0 ; 9 8 ] [ 1 ; 1 1 7 ]
    [ 2 ; 1 2 2 ] [ 3 ; 1 2 2 ] } ] [ 3 / 4 ; @ : 2 = 1 ] [ 4 / 5 ; @ : 3
     / 1 1 = 1 ] [ @ : 2 + 0 ; @ : 2 / 7 = @ : 3 / 1 1 ] [ @ : 2 + 1 ; @ :
    3 / 7 = 3 ] [ @ : 2 + 2 ; @ : 1 / 3 = @ : 0 + 1 ] [ @ : 3 + 0 ; @ : 1
     = @ : 6 / 7 ] [ @ : 3 + 1 ; @ : 1 = { [ 0 ; 5 8 ] [ 1 ; 3 2 ] } ] [ @
    : 3 + 2 ; { [ 1 ; @ : 1 = @ : 1 / 1 1 ] } : ( ^ ( ( @ : 3 / 1 1 ) / 3
     ) ? = 1 ) ] [ @ : 3 + 4 ; { [ 1 ; @ : 1 = @ : 2 / 1 1 ] } : ( ^ ( ( @
    : 3 / 1 1 ) / 5 ) ? = 1 ) ] [ @ : 3 + 5 ; @ : 3 / 1 1 = @ : 3 / 1 1 +
     1 ] [ @ : 3 + 6 ; @ : 1 = { [ 0 ; 1 0 ] } ] [ @ : 3 + 7 ; { [ 1 ; @ :
    2 = @ : 0 + 1 ] } : ( @ : 3 / 1 1 < 1 0 1 ) ] [ @ : 1 / 2 ; @ : 1 / 5
     = @ : 0 + 3 ] [ @ : 1 / 5 - 2 ; @ : 4 / 5 = 0 ] [ @ : 1 / 5 - 1 ; @ :
    ( 0 - 1 ) / 5 = @ : 2 / 5 ] [ @ : 1 / 5 + 0 ; @ : 4 / 5 = @ : 4 / 5 +
     1 ] [ @ : 1 / 5 + 2 ; @ : ( 0 - 1 ) / 5 = ( @ : ( 0 - 1 ) / 5 ) / 1 0
    ] [ @ : 1 / 5 + 3 ; { [ 1 ; @ : 1 / 5 = @ : 0 + 1 ] } : ! ( @ : ( 0 -
     1 ) / 5 < 1 ) ] [ @ : 1 / 5 + 4 ; @ : ( @ : 3 / 5 ) = @ : 0 + 1 ] [ @
    : 1 / 3 ; @ : 1 / 7 = @ : 0 + 1 ] [ @ : 1 / 7 + 0 ; @ : 6 / 7 = { } ]
     [ @ : 1 / 7 + 1 ; @ : ( 0 - 1 ) / 7 = @ : 2 / 7 ] [ @ : 1 / 7 + 2 ; @
    : 2 / 5 = @ : 2 / 7 ] [ @ : 1 / 7 + 3 ; @ : 3 / 5 = 1 / 1 3 ] [ @ : 1
     / 7 + 4 ; @ : 1 / 2 = @ : 0 + 1 ] [ @ : 1 / 1 3 + 0 ; @ : ( 0 - 2 ) /
    7 = @ : 4 / 5 ] [ @ : 1 / 1 3 + 1 ; @ : ( 0 - 3 ) / 7 = 0 ] [ @ : 1 /
     1 3 + 2 ; { [ 0 ; @ : 1 / 1 7 = @ : 0 + 1 ] [ 1 ; @ : ( @ : 3 / 7 ) =
    @ : 0 + 1 ] } : ( @ : ( 0 - 2 ) / 7 ? = 0 ) ] [ @ : 1 / 1 7 + 0 ; @ :
     ( 0 - 4 ) / 7 = ( @ : ( 0 - 1 ) / 7 - @ : ( 0 - 3 ) / 7 ) / 1 0 ] [ @
    : 1 / 1 7 + 1 ; { [ 0 ; @ : 1 / 1 9 = @ : 0 + 1 ] [ 1 ; @ : 1 / 2 3 =
     @ : 0 + 1 ] } : ( ^ ( @ : ( 0 - 4 ) / 7 ) ? = 1 ) ] [ @ : 1 / 1 9 + 0
    ; @ : ( 0 - 3 ) / 7 = @ : ( 0 - 3 ) / 7 + 1 ] [ @ : 1 / 1 9 + 1 ; @ :
     1 / 1 3 = @ : 0 - 1 ] [ @ : 1 / 2 3 + 0 ; @ : ( 0 - 2 ) / 7 = @ : ( 0
    - 2 ) / 7 - 1 ] [ @ : 1 / 2 3 + 1 ; ( @ : 6 / 7 ) : ( @ : ( 0 - 2 ) /
     7 ) = @ : ( 0 - 3 ) / 7 + 4 8 ] [ @ : 1 / 2 3 + 2 ; @ : ( 0 - 1 ) / 7
    = @ : ( 0 - 4 ) / 7 ] [ @ : 1 / 2 3 + 3 ; @ : 1 / 1 3 = @ : 0 - 0 ] }