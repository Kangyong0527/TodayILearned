# TodayILearned
## 2021.06.28 JS/Node
+ Array의 기본 Method
  + 1.[Array.length](1.-Array.length)
  + 2.[Array.indexOf](2.-Array.indexOf)
  + 3.[Array.includes](3.-Array.includes)
  + 4.[Array.push](4.-Arry.push)
  + 5.[Array.pop](5.-Array.pop)
  + 6.[Array.shift](6.-Array.shift)
  + 7.[Array.unshift](7.-Array.unshift)
  + 8.[Array.slice](8.-Array.slice)
  + 9.[Array.splice](9.-Array.splice)
  ***
  
  1. Array.length
  
    ```javascript
    const food = ['떡복이','치킨','피자'];
    console.log(food.length);
    // arrray food 안에 배열의 수가 몇인지 보여주는 메소드 이다. 0부터 시작해 올라간다.
    ```
  
  2. Array.indexOf
  
  ```javascript
    const food = ['떡복이','치킨','피자'];
    console.log(food.indexOf(떡볶이));
    //food.indexOf(떡볶이) = 0이다. 0부터 시작한다.
    //food.indexOf(곱창) = -1 이다. 없는 값은 -1 로서 표현다.
    //indexOf를 배열에 특정요소가 았는지 없는지 판별하고 없으면 추가하는 예시를 만들어보자

    function updateVegetablesCollection (veggies, veggie) {
    if (veggies.indexOf(veggie) === -1) {
        veggies.push(veggie);
        console.log('새로운 veggies 컬렉션 : ' + veggies);
    } else if (veggies.indexOf(veggie) > -1) {
        console.log(veggie + ' 은 이미 veggies 컬렉션에 존재합니다.');
    }
    }
    var veggies = ['potato', 'tomato', 'chillies', 'green-pepper'];
    updateVegetablesCollection(veggies, 'spinach');
    // 새로운 veggies 컬렉션 : potato, tomato, chillies, green-pepper, spinach
    updateVegetablesCollection(veggies, 'spinach');
    // spinach 은 이미 veggies 컬렉션에 존재합니다.
    ```
  
  3. Array.includes
    
    ```javascript
   // includes() 메서드는 배열이 특정 요소를 포함하고 있는지 판별합니다.

    [1, 2, 3].includes(2);     // true
    [1, 2, 3].includes(4);     // false
    [1, 2, 3].includes(3, 3);  // false
    [1, 2, 3].includes(3, -1); // true
    [1, 2, NaN].includes(NaN); // true
    ```
  
  4. Array.push
    
    ```javascript
    //push() 메서드는 배열의 끝에 하나 이상의 요소를 추가하고, 배열의 새로운 길이를 반환합니다.
    // 배열에 엘레먼트를 추가하기

    var sports = ['축구', '야구'];
    var total = sports.push('미식축구', '수영');
    console.log(sports); // ['축구', '야구', '미식축구', '수영']
    console.log(total);  // 4
    
    //두 배열 합치기

    var vegetables = ['설탕당근', '감자'];
    var moreVegs = ['셀러리', '홍당무'];

    // 첫번째 배열에 두번째 배열을 합친다.

    // vegetables.push('셀러리', '홍당무'); 하는 것과 동일하다.
    Array.prototype.push.apply(vegetables, moreVegs);
    console.log(vegetables); // ['설탕당근', '감자', '셀러리', '홍당무']
    ```
  
  5. Array.pop
  
  ```javascript
  //pop() 메서드는 배열에서 마지막 요소를 제거하고 그 요소를 반환합니다.
  //pop 메서드는 배열에서 마지막 요소를 제거하여 그 값을 호출자(caller)에게 반환합니다.

    var myFish = ['angel', 'clown', 'mandarin', 'sturgeon'];
    var popped = myFish.pop();
    console.log(myFish); // ['angel', 'clown', 'mandarin' ]
    console.log(popped); // 'sturgeon']
    ```
  
  6. Array.shift
 
  ```javascript
  //shift() 메서드는 배열에서 첫 번째 요소를 제거하고, 제거된 요소를 반환합니다. 이 메서드는 배열의 길이를 변하게 합니다.

  const array1 = [1, 2, 3];
  const firstElement = array1.shift();
  console.log(array1);
  // expected output: Array [2, 3]
  console.log(firstElement);
  // expected output: 1
  ```
  
  7. Array.unshift
  
  ```javascript
  //unshift() 메서드는 새로운 요소를 배열의 맨 앞쪽에 추가하고, 새로운 길이를 반환합니다.

  const array1 = [1, 2, 3];
  console.log(array1.unshift(4, 5));
  // expected output: 5
  console.log(array1);
  // expected output: Array [4, 5, 1, 2, 3]
  ```

  8. Array.slice

  ```javascript
  // slice() 메서드는 어떤 배열의 begin부터 end까지(end 미포함)에 대한 얕은 복사본을 새로운 배열 객체로 반환합니다. **원본 배열은 바뀌지 않습니다**.
  const animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

  console.log(animals.slice(2));
  // expected output: Array ["camel", "duck", "elephant"]

  console.log(animals.slice(2, 4));
  // expected output: Array ["camel", "duck"]

  console.log(animals.slice(1, 5));
  // expected output: Array ["bison", "camel", "duck", "elephant"]

  console.log(animals.slice(-2));
  // expected output: Array ["duck", "elephant"]

  console.log(animals.slice(2, -1));
  // expected output: Array ["camel", "duck"]

  // slice(beigin,end)
  /* begin
    0을 시작으로 하는 추출 시작점에 대한 인덱스를 의미합니다.
     음수 인덱스는 배열의 끝에서부터의 길이를 나타냅니다. slice(-2) 는 배열에서 마지막 두 개의 엘리먼트를 추출합니다.
    begin이 undefined인 경우에는, 0번 인덱스부터 slice 합니다.
    begin이 배열의 길이보다 큰 경우에는, 빈 배열을 반환합니다.
    
    end
    추출을 종료 할 0 기준 인덱스입니다. slice 는 end 인덱스를 제외하고 추출합니다.
    예를 들어, slice(1,4)는 두번째 요소부터 네번째 요소까지 (1, 2 및 3을 인덱스로 하는 요소) 추출합니다.
    음수 인덱스는 배열의 끝에서부터의 길이를 나타냅니다. 예를들어 slice(2,-1) 는 세번째부터 끝에서 두번째 요소까지 추출합니다
    ```

  9. Array.splice 
  ```javascript
  //splice() 메서드는 배열의 기존 요소를 삭제 또는 교체하거나 새 요소를 추가하여 배열의 내용을 변경합니다.
  //array.splice(start[, deleteCount[, item1[, item2[, ...]]]])  
  const months = ['Jan', 'March', 'April', 'June'];
  months.splice(1, 0, 'Feb');
  // inserts at index 1
  console.log(months);
  // expected output: Array ["Jan", "Feb", "March", "April", "June"]

  months.splice(4, 1, 'May');
  // replaces 1 element at index 4
  console.log(months);
  // expected output: Array ["Jan", "Feb", "March", "April", "May"]

  //array.splice(시작인덱스,제거할 갯수,추가할 인자들) 이렇게 사용한다.
  //음수가 시작인데스로 온다면 뒤에서 부터 새는 것이다.








  



