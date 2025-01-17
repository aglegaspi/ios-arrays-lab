# Arrays lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.

## Question 1 √

Create an array of strings called `colors` that contain "orange", "red", "yellow", "turquoise", and "lavender".

Then, using array subscripting and string interpolation, print out the String `"orange, yellow, and lavender are some of my favorite colors"`.

```swift

let colors = ["orange","red","yellow","turquoise","lavender"]

print("\(colors[0]), \(colors[2]), and \(colors[4]) are some of my favorite colors")

```

## Question 2 √

Remove "Illinois" and "Kansas" from the array below.

`var westernStates = ["California", "Oregon", "Washington", "Idaho", "Illinois", "Kansas"]`

```swift
westernStates.popLast()
westernStates.popLast()

print(westernStates)
```

## Question 3 √

Iterate through the array below. For each state, print out the name of the state, a colon, and whether it is or is not **in the continental United States.**

`let moreStates = ["Hawaii", "New Mexico", "Alaska", "Montana", "Texas", "New York", "Florida"]`

```swift

for s in moreStates {
    if s != "Hawaii" && s != "Alaska" {
        print("\(s): is in the continental United States")
    } else {
        print("\(s): is NOT in the continental United States")
    }
}

```


## Question 4 √

Print out how many non-whitespace characters are in `myString`:

`let myString = "This is good practice with Strings!"`

```swift

let trimString = myString.trimmingCharacters(in: .whitespaces).count

```

Iterate through the array below. For each sentence, print out how many non-whitespace characters are in it.

`let myFavoriteQuotes = ["To be or not to be, that is the question.", "The only source of knowledge is experience.", "Mr. Gorbachev, tear down this wall!", "Four score and twenty years ago..."]`

```swift 

let myFavoriteQuotes = ["To be or not to be, that is the question.", "The only source of knowledge is experience.", "Mr. Gorbachev, tear down this wall!", "Four score and twenty years ago..."]

for (_, value) in myFavoriteQuotes.enumerated() {
ß
    let charNWCount = value.replacingOccurrences(of: " ", with: "").count
    
    print(charNWCount)
}


```


## Question 5 √

Iterate through `garden` and place any 🌷 that you find into the `basket`. Replace any 🌷 that you pick up with `"dirt"`. Then print how many 🌷 are in your `basket`.

```swift
var garden = ["dirt","🌷","dirt","🌷","dirt","dirt","🌷","dirt","🌷","dirt"]
var basket = [String]()
```
```swift

for (index,value) in garden.enumerated() where value == "🌷" {
    basket.append(value)
    garden[index] = "dirt"
}

print(basket)
print(garden)

```

## Question 6 √

The below array represents an unfinished batting lineup for a baseball team. **You, the coach,** need to make some last minute changes:

- Add "Suzuki" to the end of your lineup.
- Change "Jeter" to "Tejada".
- Change "Thomas" for "Guerrero"
- Put "Reyes" to bat 8th instead.

`var battingLineup = ["Reyes", "Jeter", "Ramirez", "Pujols","Griffey","Thomas","Jones", "Rodriguez"]`

```swift

var battingLineup = ["Reyes", "Jeter", "Ramirez", "Pujols","Griffey","Thomas","Jones", "Rodriguez"]

battingLineup += ["Suzuki"]
battingLineup[1] = "Tejada"
battingLineup[5] = "Guerrero"
battingLineup.remove(at: 0)
battingLineup += ["Reyes"]

print(battingLineup)

```

## Question 7 √

Given an array of Ints, find out if it contains a target number.  

(The built-in `contains(_:)` function will do this, but you aren't allowed to use it for this exercise.)


Ex.1

```swift
numbers = [4,2,6,73,32,4,2,1]

target = 32

//true
```

Ex. 2

```swift
numbers = [32459,2,4,5,1,4,2,1]

target = 3

//false
```


```swift

let numbers = [4,2,6,73,32,4,2,1]

var numbers: [Int]
let target: Int = 32

for n in numbers {
    if n == target {
        print("found the target number \(target)")
    }
}

```


## Question 8 √

Find the largest value in an array of Int.  Do not use the built-in `max()` method.

```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

//This creates an array of 100 numbers in between 0 and 200.  For now, you don't need to worry about how it does that.
```
```swift

let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

var maxNum = 0

for i in arrayOfNumbers where i > maxNum {
    maxNum = i
}
print(maxNum)

```


## Question 9 √

Find the smallest value in an array of Int.  Do not use the built in min() method.

```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

//This creates an array of 100 numbers in between 0 and 200.  For now, you don't need to worry about how it does that.
```

```swift

let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

var minNum = arrayOfNumbers.max() ?? 0

for i in arrayOfNumbers where i < minNum {
    minNum = i
}
print(minNum)


```


## Question 10 √

Iterate through `secondListOfNumbers`, and print out all the odd numbers.

`var secondListOfNumbers = [19,13,14,19,101,10000,141,404]`

```swift 

var secondListOfNumbers = [19,13,14,19,101,10000,141,404]

for n in secondListOfNumbers where n % 2 == 1 {
    print(n)
}

```


## Question 11√

Iterate through `thirdListOfNumbers`, and print out the sum.

`var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]`

```swift

var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]
let result = thirdListOfNumbers.reduce(0,+)

````


## Question 12 √

Iterate through `thirdListOfNumbers`, and print out the sum of all the even numbers.

`var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]`

```swift 

var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]
var sumOfEvens = 0

for n in thirdListOfNumbers {
    if n % 2 == 0 {
        sumOfEvens += n
    }
}
print(sumOfEvens)

```

## Question 13 √

Append every Int that appears in both `listOne` and `listTwo` to the `sharedElements` array. Then print **how many Ints** are shared.

```swift
var listOne = [28, 64, 7, 96, 13, 32, 94, 11, 80, 68]
var listTwo = [18, 94, 48, 6, 42, 68, 79, 76, 13, 7]
var sharedElements = [Int]()
```

```swift

for i in listOne {
    for j in listTwo {
        if i == j {
            sharedElements.append(i)
        }
    }
}
print(sharedElements.count)


```


## Question 14 √

Write code such that `noDupeList` has all the same Ints as `dupeFriendlyList`, but has no more than one of each Int.

```swift

var dupeFriendlyList = [4,2,6,2,2,6,4,9,2,1]
var noDupeList: [Int] = []

// filter WHERE Ints are NOT noDupeList and then append that value to the noDupeList array.
for i in dupeFriendlyList where !noDupeList.contains(i) {

    noDupeList.append(i)
}
print(noDupeList)

```

## Question 15 √

Find the second smallest number in an Array of Ints

```swift

let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

let sortArr = arrayOfNumbers.sorted()
let secondSmNum = sortArr[1]
print(secondSmNum)

```

## Question 16 √

If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Find the sum of all the multiples of 3 or 5 below 1000.

```swift

var sum = 0
for i in 1..<1000 where i % 3 == 0 || i % 5 == 0 {
    sum += i
}
print(sum)

```

## Question 17 √

Make an array that contains all elements that appear **more than twice** in `someRepeatsAgain`.

```swift
var someRepeatsAgain = [25,11,30,31,50,28,4,37,13,20,24,38,28,14,44,33,7,43,39,35,36,42,1,40,7,14,23,46,21,39,11,42,12,38,41,48,20,23,29,24,50,41,38,23,11,30,50,13,13,16,10,8,3,43,10,20,28,39,24,36,21,13,40,25,37,39,31,4,46,20,38,2,7,11,11,41,45,9,49,31,38,23,41,16,49,29,14,6,6,11,5,39,13,17,43,1,1,15,25]

let dups = Dictionary(grouping: someRepeatsAgain, by: {$0}).filter { $1.count > 1 }.keys.sorted()
print(dups)

```

## Question 18 √

Identify if there are 3 integers that sum to 10 in the following array. If so, print them as a triplet. If there are multiple triplets, print all possible triplets.

`var tripleSumArr = [-20,-14,-8,-5,-3,-2,1,2,3,4,9,15,20,30]`

```swift 

var tripleSumArr = [-20,-14,-8,-5,-3,-2,1,2,3,4,9,15,20,30]

for i in 0...tripleSumArr.count - 3 {

    for j in 1...tripleSumArr.count - 2 {
    
        for k in 2...tripleSumArr.count - 1 {
        
            if tripleSumArr[i] + tripleSumArr[j] + tripleSumArr[k] == 10 {
                print("\(tripleSumArr[i]) \(tripleSumArr[j]) \(tripleSumArr[k])")
            }
        }
    }
}

```


## Question 19 √

Given an array of Strings, find the the String with the most "a"s in it.

input: `["apes", "abba", "apple"]`
output: `"abba"`

```swift

let input19 = ["apes", "abba", "apple"]
var counter = 0
var counterArr = [Int]()

for str in input19 {
    
    for letter in str where String(letter).contains("a") {
        counter += 1
    }
    counterArr.append(counter)
    counter = 0
}

print(input19[counterArr.max()! - 1])


```


## Question 20 √

Given an Array of Arrays of Ints, find the Array of Ints with the largest sum:

Input: `[[2,4,1],[3,0],[9,3]]`
Output: `[9,3]`

```swift

let input20 = [[2,4,1],[3,0],[9,3]]
var result20 = [Int]()
var largSum = 0

for array in input20 {
    var sum = array.reduce(0,+)

    if sum > largSum {
        largSum = sum
        result20 = array
    }
}
print(result20)

```


## Question 21 √

Given an Array of Tuples of type `(Int, Int)`, create an array containing all the tuples where the first Int is equal to the second Int.

Input: `[(4,2), (-3,-3), (1,1), (3,9)]`
Output: `[(-3,-3), (1,1)]`

```swift

let arrTups = [(4,2), (-3,-3), (1,1), (3,9)]
var tupleArray: [(Int,Int)] = []

for tuple in arrTups where tuple.0 == tuple.1 {
    tupleArray.append(tuple)
}
print(tupleArray)

```

## Question 22 √

Given an Array of Bools, make a variable called `allAreTrue` that is true if all of the Bools are true and false if any of them are false.

Input: `[true, false, true, true]`

Output: `false`

```swift

let arrBools = [true, true, true, true]

var allAreTrue: [Bool] = []
var trueCount = 0

for b in arrBools {

    if b == false {
        allAreTrue = [false]
    break
    }

    if b == true {
        trueCount += 1
    }

    if trueCount == arrBools.count {
        allAreTrue = [true]
    }

}
print(allAreTrue)


```

## Question 23 √

Given an Array of Ranges of Ints, create an array that has all the values from all the ranges in order from smallest to greatest with no duplicates.

Input: `[0..<3 , 2..<10, -4..<6, 13..<14]`

Output: `[-4,-3,-2,-1,0,1,2,3,4,5,6,7,8,9,10,13]`

```swift

let input23 = [0..<3 , 2..<10, -4..<6, 13..<14]
var output23 = [Int]()

for range in input23 {

    // find WHERE number is not in the output then add it to the array 
    
    for num in range where !output23.contains(num) {
        output23 += [num]
    }
}

output23.sort()
print(output23)

```


## Question 24 √

Given an array of Characters, create a String ignoring and uppercase Characters and spaces.  Then uppercase every other character of the String.

Input: `let arr: [Character] = ["a", "p","P","l","E"," ","S","a","u","C,"e"]`
Output: `"ApLeAuE"`

```swift

let arr: [Character] = ["a","p","P","l","E"," ","S","a","u","C","e"]

var output = String()
var count = 1

// iterate & filter out spaces and uppercase letters
for char in arr where char != " " && char != Character(char.uppercased()) {


    if count % 2 == 0 {
        output += String(char)
    } else {
    
        output += String(char.uppercased())
    }
    count += 1
}
print(output)

```


## Question 25 √

Print out each element in `myMatrix`

`var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]`

```swift

var myMatrix1 = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]

for arr in myMatrix1 {
    
    for elem in arr {
        print(elem)
    }
}

```

## Question 26 √

Print out the sum of the diagonals of `myMatrix`.

`var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]`

```swift

var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]

//declare a sum variable for each
var sum1 = 0
var sum2 = 0
var sum3 = 0


for arr in myMatrix {
    
    for (index, num) in arr.enumerated() {
    
        // if the index is zero we will add each value to that sum
        if index == 0 {
            sum1 += num
        }
        // if the index is one we will add each value to that sum
        if index == 1 {
            sum2 += num
        }
        // if the index is two we will add each value to that sum
        if index == 2 {
            sum3 += num
        }
    }
}

print(sum1)
print(sum2)
print(sum3)

```

```swift



```

## Question 27 √

Using for loops, rotate `matrixToRotate` 90 degrees.
var matrixToRotate = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
![Matrix Rotation](images/rotated_matrix.jpeg)

```swift

var matrixToRotate = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
var matrix90: Array = [[0,0,0], [0,0,0], [0,0,0]]

for (index, array) in matrixToRotate.enumerated() {
    
    // when index is zero update each matrix90[index][2] with the values from matrixToRotate[0][0]
    
    if index == 0 {
        var count = 0
        
        for number in array {
            if count < 3 {
                matrix90[count][2] = number
                count += 1
            }
        }
        count = 0
    }
    
    // when index is one update each matrix90[index][1] with the values from matrixToRotate[0][1]
    
    if index == 1 {
        var count = 0
        
        for number in array {
            if count < 3 {
                matrix90[count][1] = number
                count += 1
            }
        }
        count = 0
    }
    
    // when index is one update each matrix90[index][0] with the values from matrixToRotate[0][2]
    
    if index == 2 {
        var count = 0
        
        for number in array {
            if count < 3 {
                matrix90[count][0] = number
                count += 1
            }
        }
        count = 0
    }
}

print(matrix90)


```
