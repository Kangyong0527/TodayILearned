#Object

## Object 란 무엇인가.

```javascript 
const courseA{
    Appetizer : wine,
    main : steak,
    dessert : chocolet
}
```
메뉴판엔 코스A가 있다.
그 코스 안에는 에피타이져, 메인, 디져트로 구성되어있다.
이것을 객체로 보자면 
코스 A는 객체의 이름이고 에피타이져 ,메인 ,디저트는 key의 이름이다.
그 안에 값들은 value 이다.
코스A의 에피타이저를 보는 방법은 두가지인데 하나는 
courseA.Appetizer - 닷 노테이션과 
courseA['Appetizer'] - 브라켓 노테이션
두가지 이다. 두가지의 차이점에 대해 알아보자.

```javascript
course.Appetizer
course['Appetizer']
```
사실 두가지의 차이점은 크게 없다. 그러나 브라켓 노테이션을 써야 할 때가 오는데 그떄가 바로
키값이 동적일때 이다. 한마디로 객체안에 키값이 변수로 올때이다.
course.Appetizer === course.['Appetizer'] 는 true 이지만
course.Appetizer && course.['Appetizer'] === course.[Appetizer]
는 false이다.
course.[Appetizer]는 자바스크립트가 []안에 값을 변수로 보기 때문에 에러가 뜨게 된다.
그렇다면 앞서 말한 동적인 상황은 무엇일까
```javascript
let courseA = {
    Appetizer: 'wine',
    main: 'steak',
    dessert: 'chocolet'
}

function courseMenu(course,element){
    return course[element]
}

let order1 = courseMenu(courseA,'main')
//'staek' 
```
이렇게 함수로서 객체가 여러개 이고 키값또한 변수로서 들어갈때 객체[변수값] 이렇게 사용하개 된다.
이렇게 브라캣 노태이션은 변수값을 사용해야 할때 쓸 수 있다.
## delete

delete 연산자는 객체의 속성을 제거합니다.
```javascript
delete object.property
delete object['property']
```
이렇게 delete 연산자를 앞에 쓰고 객체 그리고 삭재하고자 하는 카를 써주면 삭제가 된다.

## for..in

for...in문은 상속된 열거 가능한 속성들을 포함하여 객체에서 문자열로 키가 지정된 모든 열거 가능한 속성에 대해 반복합니다. 
```javascript
var obj = {a: 1, b: 2, c: 3};
for (const prop in obj) {
  console.log(`obj.${prop} = ${obj[prop]}`);
}
// Output:
// "obj.a = 1"
// "obj.b = 2"
// "obj.c = 3"
```
예시를 보면 prop은 obj의 키값이다. for문으로 반복하며 키값을 하나씩 꺼내온다.
그라고 obj[prop]은 키값의 value 이다. 이것또한 반복하며 하나씩 꺼내온다.
이런식으로 우리가 만든 cours메뉴를 사용해 보면 이렇다
```javascript
let courseA = {
    Appetizer: 'wine',
    main: 'steak',
    dessert: 'chocolet'
}
let result2 = '';
function coursWhat(courseA){
    for (const property in courseA) {
 result2 = result2 + property + ': ' + courseA[property] + '\n'
}
return result2
}

coursWhat(courseA); //Appetizer: 'wine' main: 'steak' dessert: 'chocolet'
```

## Object.keys

Object.keys()메서드는 지정된 객체의 고유 한 열거 가능한 속성 이름 배열을 반환 하며 일반 루프와 동일한 순서로 반복됩니다.
한마디로 Object.keys는 객체의 키값만 순서대로 뽑아온다.
```javascript
const object1 = {
  a: 'somestring',
  b: 42,
  c: false
};
console.log(Object.keys(object1));
// expected output: Array ["a", "b", "c"]
```
