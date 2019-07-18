## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`

Output: `HELLO, THERE`

```swift
var greeting = "Hello, there"

greeting = greeting.uppercased()
print(greeting)
```

2. **Given a String, return a String alternating between uppercase and lowercase letters**


Input: `Hello, there`

Output: `HeLlO, tHeRe`

```swift
var greeting = "Hello, there"
var camelChaos = String()

for (key, value) in greeting.enumerated() {
if key % 2 == 0 {
camelChaos = camelChaos + value.uppercased()
} else {
camelChaos = camelChaos + "\(value)"
}
}
print(camelChaos)
```


3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`

```swift
var greeting = "Hello, there"
var removeALetter = String()

for letter in greeting {
if letter == "e" {

} else {
removeALetter = removeALetter + "\(letter)"
}
}
print(removeALetter)

// Second way to do the above
print(greeting.replacingOccurrences(of: "e", with: ""))
```
## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`

```swift
var numNums = [1,5,2,4,1,4]

numNums.reduce(0, {(x, y) -> Int in
return x > y ? x : y
})
```

2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`

Output: `1`

```swift
var numNums = [1,5,2,4,1,4]

numNums.reduce(numNums[0], {(x, y) -> Int in
return x < y ? x : y
})
```

3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`

Output: `17`

```swift
var numbers = [1,5,2,4,1,4]
var sum = Int()

for nums in numbers {
sum += nums
}
print(sum)
```

4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`

```swift
var numbers: [Double] = [3,4.5,7.5,2,1]
var average = Double()
for nums in numbers {
average += nums / Double(numbers.count)
}
print(average)
```

5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`

```swift
var numbers: [Double] = [3,4.5,7.5,2,1]
var greaterThanThisNumber: Double = 3
var sum = Double()
for nums in numbers {
if nums > greaterThanThisNumber {
sum += nums
}
}
print(sum)
```

6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`

```swift
var numNums: [Double] = [3,4.5,7.5,2,1]
var product = Double()

for nums in numNums {
if product == 0.0 {
product += 1.0
}
product *= nums
}
print(product)
```

7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`

```swift
var numbers = [3,6,1,9,4,8]
numbers.sorted()
print(numbers.sorted()[1])
```
## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`

Output: `["We", "come", "in", "peace"]`

```swift
var string = [nil, "We", "come", nil, "in", "peace"]
var unwrappedString: [String] = []

for words in string {
if let word = words {
unwrappedString.append(word)
}
}
print(unwrappedString)
```

2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`
```swift
var array: [String?]? = nil
var answer: [String] = []

if let realArray = array {
for string in realArray {
if let realString = string {
answer.append(realString)
}
}
}
print(answer)

```
3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18`

```swift
var arrayOfInts = [4, nil, 9, 5, nil]
var sum = Int()

for ints in arrayOfInts {
guard ints != nil else {
continue
}
sum += ints!
}

print(sum)
```

4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`

```swift
var arrayOfInts: [Int?]? = nil
var sum = Int()

if let _ = arrayOfInts {
for ints in arrayOfInts! {
guard ints != nil else {
continue
}
sum += ints!
}
}
print(sum)
```

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`

```swift
var array = [1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3]
var optionalInt: Int? = 1
var realInt = Int()
var sum = Int()
if let unwrapped = optionalInt {
realInt += unwrapped
}
for ints in array {
if let int = ints, int != realInt {
sum += int
}
}
print(sum)
```
## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`

```swift
var fruits: [Int:String] = [1:"apple", 2:"apple", 3:"banana", 4:"banana", 5:"banana", 6:"cake", 7:"cake"]
var output: [String] = []
for value in fruits.values {
if output.contains(value) {
continue
} else {
output.append(value)
}
}
print(output)
```

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t`

```swift
var sentence = "Never trust a computer you can't throw out a window ~ Steve Wozniak"
var lettersToFrequence: [Character:Int] = [:]
sentence = sentence.replacingOccurrences(of: " ", with: "")
for character in sentence.lowercased() {
var count = Int()
for frequency in sentence.lowercased() {
if frequency == character {
count += 1
}
}
lettersToFrequence[character] = count
}
print(lettersToFrequence)
var chara = ""
var mostFrequent = Int()
for (key,value) in lettersToFrequence {
if value > mostFrequent {
mostFrequent = value
chara = "\(key)"
}
}
print(chara)
```

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`

```swift
var input = [1,1,2,3,3,3,4,5,6,6,7]
var intsToFrequency: [Int:Int] = [:]
var output: [Int] = []
for numbers in input {
var counter = Int()
for innerLoop in input {
if numbers == innerLoop {
counter += 1
}
}
intsToFrequency[numbers] = counter
}

print(intsToFrequency)

for (key,value) in intsToFrequency {
if value >= 2 {
output.append(key)
}
}
print(output)
```

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`
```swift
var sentence = "Never trust a computer you can't throw out a window ~ Steve Wozniak"
var lettersToFrequence: [Character:Int] = [:]
sentence = sentence.replacingOccurrences(of: " ", with: "")
var secondMost: [Int] = []
var second = Int()
for character in sentence.lowercased() {
var count = Int()
for frequency in sentence.lowercased() {
if frequency == character {
count += 1
}
}
lettersToFrequence[character] = count
}

for value in lettersToFrequence.values {
secondMost.append(value)
}
secondMost.count
secondMost = secondMost.sorted()
second = secondMost[19]
print(second)

for (key,value) in lettersToFrequence {
if value == second {
print(key)
}
}
```

## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`

```swift
var input = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

print(input.sorted())

```
2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`

```swift
var input = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

input.sort(by: {(x,y) in x.count < y.count})
print(input)
```
3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`

```swift
var input = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]
var output = input.filter({(x) in
x.count >= 4
})
print(output)
```

4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`

```swift
var input = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

let altogetherNow = input.reduce("", {if $0 == "" {return $1} else {return $0 + " " + $1}})
print(altogetherNow)
```

## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**
Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`

```swift
let number = [1,2,3,4,5,6]
enum NumberType {

case even
// Even numbers can be found by using the argument, "Number % 2 == 0"

case odd
// Odd numbers can be found by using the argument, "Number % 2 != 0"

func evenOrOdd(arr: [Int]) -> [Int] {
var numArr: [Int] = [] //This array will have the numbers appended to it depending on the case
switch self { //Refers to instance of NumberType. Looks at its own value. In this case, it would be even or odd.
case .even: //Conditions to check for even numbers + append
for numbers in arr {
if numbers % 2 == 0 {
numArr.append(numbers)
}

}

case .odd: //Conditions to check for odd numbers + append
for numbers in arr {
if numbers % 2 != 0 {
numArr.append(numbers)
}
}
}
return numArr //returns the array with the appeneded numbers
}
}
let even = NumberType.even //Instance of NumberType that has the member value, 'even'.
print(even.evenOrOdd(arr: number))
```

2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
enum StringType {
    case lowercase
    case uppercase
}
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``

```swift
```swift
var input = "Design is not just what it looks like and feels like. Design is how it works"

enum StringType {
case lowercase
case uppercase

func upperOrLower(string: String) -> String {
switch self {
case .lowercase:
return string.lowercased()
case .uppercase:
return string.uppercased()
}
}
}
var upper = StringType.uppercase
print(upper.upperOrLower(string: input))
```
3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`
