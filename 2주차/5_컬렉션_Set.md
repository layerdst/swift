## 규칙
- 대괄호 묶음, 배열과 구분이 안되기 때문에 반드시 생성시 타입을 선언해야함
```swift
let set : Set<Int> = [1,2,3,4]
let set : Set = [1,2,3,4]
let emptySet : Set<Int> = []
let emptySet1 = Set<Int>()
```
- 요소값을 중복으로 넣어도, 집합의 의미상 요소가 중복으로 저장이 되지 않음
- 순서가 보장이 안됨
```swift
let set : Set<Int> = [1,2,3,3,5]
print(set) // [1,2,3,5]
```

- 각 요소는 유일한 값 Hashable, 검색속도가 빠름 

### 기본기능
```swift
set.count
set.isEmpty

set.contains(1)
set.randomElement() //Optional
```

### Update(insert, replace, append)
- 서브스크립트 관련 문법은 없다
```swift
set.update(with:1) //Int? 1이라는 요소를 추가한다.
set.update(with:7) // 새로운 요소가 추가되면 nil 을 반환한다.
```

### remove 
```swift
set.remove(1) // Optional(1) 삭제한 요소를 리턴함
set.remove(8) // 존재하지 않는 요소를 삭제할 때 nil을 반환함. 에러는 발생하지 않음

set.removeAll()
set.removeAll(keepCapacity:true)
```

### Set 의 비교
```swift
var a : Set = [1,2,3,4,5,6,7,8,9]
var b : Set = [1,3,5,7,9]
var c : Set = [2,4,6,8,10]
var d : Set = [3,5,7,9,1]

b==d // true
```

### 부분집합, 합집합, 서로소, 상위집합
```swift
b.isSubset(of:a) // b는 a의 부분집합 여부 true
b.isStrictSubset(of:a) // 진부분집합 false

a.isSuperset(of:b) // a는 b의 상위집합
a.isStrictSuperset(of:b) // a 는 b 의 진상위집합 여부

d.isDisjoint(with:c) // 서로소 여부
```

### 합집합
```swift
var unionSet = b.union(c) // 
//b.formUnion(c) // 원본변경
```

###  교집합
```swift
var interSet = a.intersection(b)
//a.formIntersection(b)
```

## 차집합
```swift
var subSet = a.subtracting(b)
// a.subtract(b) // 원본변경
```
### 대칭차집합
```swift
var symetricSet = a.symetricDifference(b)
//a.formSymmetricDifference(b)
```
### 반복문과의 결합
```swift
let interatingSet : Set = [1,2,3]
var newArray : Array = newSet.sorted()

for(num in interatingSet){
    print(num)
}

```


