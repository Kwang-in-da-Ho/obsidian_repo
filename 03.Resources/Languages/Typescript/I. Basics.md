# 1. Basic Types
```javascript
// TS 문자열 선언
let str_ts: string = 'hello';

// TS 숫자형 변수 선언
let num: number = 10;

// TS 배열 선언
let arr_num: Array<number> = [1, 2, 3];
let arr_num2: number[] = [4, 5, 6];
// let arr: number[] = [7, 8, '9'];

let arr_str: Array<string> = ['aaa', 'bbb', 'ccc'];

// TS tuple
// tuple : 모든 요소의 타입이 각각 정의된 배열
let address: [string, number] = ['gangnam', 91234];

// TS Object
let obj: object = {};
let person: object = {
    name : 'horilla'
    , age : 30
};
// 객체의 각 property의 타입까지 지정하는 방법
let person2: { name: string, age: number } = {
    name : 'horilla'
    , age : 30
}

// TS Boolean
let show: boolean = true;
```
# 2. Functions
```javascript
// 함수의 파라미터, 리턴 값의 타입을 정의
function sum(a: number, b:number): number{
    return a + b;
}

// JS와 다르게 인자의 개수에 대한 유연함이 없다
// sum(10, 20, 30, 40); => compile error
sum(10, 20);


// 함수의 optional prameter => '?'
function print_str(a: string, b?: string, c?: string){
    console.log(a + b + c);
}

print_str('aaa');
print_str('aaa', 'bbb');
print_str('aaa', 'bbb', 'ccc');
```
