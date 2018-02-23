# swiftfmt

A tool for formatting Swift code according to style guidelines.

### A Work In Progress
swiftfmt is still in active development.




Configurations
---------------------------------------

### Tabs and Indents

**Use tab character**

```diff
 class Shape {
-    var numberOfSides = 0
-    func simpleDescription() -> String {
-        return "A shape with \(numberOfSides) sides."
-    }
+       var numberOfSides = 0
+
+       func simpleDescription() -> String {
+               return "A shape with \(numberOfSides) sides."
+       }
 }

```

**Indent**

`"indent" : 2`

```diff
 class Shape {
-    var numberOfSides = 0
-    func simpleDescription() -> String {
-        return "A shape with \(numberOfSides) sides."
-    }
+  var numberOfSides = 0
+
+  func simpleDescription() -> String {
+    return "A shape with \(numberOfSides) sides."
+  }
 }

```

**Keep indents on empty lines**

```diff
 class Shape {
     var numberOfSides = 0
+    
     func simpleDescription() -> String {
         return "A shape with \(numberOfSides) sides."
     }
```

**Indent 'case' branches**

```diff
 let someCharacter: Character = "z"
 switch someCharacter {
-case "a":
-    print("The first letter of the alphabet")
-case "z":
-    print("The last letter of the alphabet")
-default:
-    print("Some other character")
+    case "a":
+        print("The first letter of the alphabet")
+    case "z":
+        print("The last letter of the alphabet")
+    default:
+        print("Some other character")
 }
```

### Spaces

#### Before Parentheses

**Method/function declaration parentheses**

```diff
 class Counter {
     var count = 0
-    
-    func increment() {
+
+    func increment () {
         count += 1
     }
 
-    func increment(by amount: Int) {
+    func increment (by amount: Int) {
         count += amount
     }
 
-    func reset() {
+    func reset () {
         count = 0
     }
 }
```

**Method/function call parentheses**

```diff
 struct Point {
     var x = 0.0, y = 0.0
+
     mutating func moveBy(x deltaX: Double, y deltaY: Double) {
-        self = Point(x: x + deltaX, y: y + deltaY)
+        self = Point (x: x + deltaX, y: y + deltaY)
     }
 }
```

**'if' parentheses**

```diff
-if(temperatureInFahrenheit <= 32) {
+if (temperatureInFahrenheit <= 32) {
     print("It's very cold. Consider wearing a scarf.")
-} else if(temperatureInFahrenheit >= 86) {
+} else if (temperatureInFahrenheit >= 86) {
     print("It's really warm. Don't forget to wear sunscreen.")
 }
```

**'while' parentheses**

```diff
 var square = 0
 var diceRoll = 0
-while(square < finalSquare) {
+while (square < finalSquare) {
     // roll the dice
     diceRoll += 1
     if diceRoll == 7 { diceRoll = 1 }
```

**'switch' parentheses**

```diff
 let someCharacter: Character = "z"
-switch(someCharacter) {
+switch (someCharacter) {
 case "a":
     print("The first letter of the alphabet")
 case "z":
```

**'catch' parentheses**

**Attribute parentheses**

#### Around Operators

**Assignment Operators (=, +=, ...)**

```diff
-let contentHeight=40
-let hasHeader=true
+let contentHeight = 40
+let hasHeader = true
 let rowHeight: Int
 if hasHeader {
-    rowHeight=contentHeight+50
+    rowHeight = contentHeight + 50
 } else {
-    rowHeight=contentHeight+20
+    rowHeight = contentHeight + 20
 }
```

**Logical Operators (&&, ||)**

```diff
-if enteredDoorCode&&passedRetinaScan||hasDoorKey||knowsOverridePassword {
+if enteredDoorCode && passedRetinaScan || hasDoorKey || knowsOverridePassword {
     print("Welcome!")
 } else {
     print("ACCESS DENIED")
```

**Equality Operator (==)**

```diff
 let name = "world"
-if name=="world" {
+if name == "world" {
     print("hello, world")
 } else {
     print("I'm sorry \(name), but I don't recognize you")
```

**Relational Operators (<, >, <=, >=)**

```diff
-2>1    // true because 2 is greater than 1
-1<2    // true because 1 is less than 2
-1>=1   // true because 1 is greater than or equal to 1
-2<=1   // false because 2 is not less than or equal to 1
+2 > 1 // true because 2 is greater than 1
+1 < 2 // true because 1 is less than 2
+1 >= 1 // true because 1 is greater than or equal to 1
+2 <= 1 // false because 2 is not less than or equal to 1
```

**Bitwise Operators (&, |, ^)**

**Additive Operators (+, -)**

**Multiplicative Operators (*, /, %)**

**Shift Operators (<<, >>)**

**Range Operators (..., ..<)**

```diff
-for index in 1 ... 5 {
+for index in 1...5 {
     print("\(index) times 5 is \(index * 5)")
 }
```

**Closure Arrow (->)**

```diff
-func greet(person: String)->String {
+func greet(person: String) -> String {
     let greeting = "Hello, " + person + "!"
     return greeting
 }
```

#### Before Left Brace

**Type declaration left brace**

```diff
-struct Resolution{
+struct Resolution {
     var width = 0
     var height = 0
 }
-class VideoMode{
+
+class VideoMode {
     var resolution = Resolution()
     var interlaced = false
     var frameRate = 0.0
```

**Method/function left brace**

```diff
-func greet(person: String) -> String{
+func greet(person: String) -> String {
     let greeting = "Hello, " + person + "!"
     return greeting
 }
```

**'if' left brace**

```diff
 var temperatureInFahrenheit = 30
-if temperatureInFahrenheit <= 32{
+if temperatureInFahrenheit <= 32 {
     print("It's very cold. Consider wearing a scarf.")
 }
```

**'else' left brace**

```diff
 temperatureInFahrenheit = 40
 if temperatureInFahrenheit <= 32 {
     print("It's very cold. Consider wearing a scarf.")
-} else{
+} else {
     print("It's not that cold. Wear a t-shirt.")
 }
```

**'for' left brace**

```diff
 let names = ["Anna", "Alex", "Brian", "Jack"]
-for name in names{
+for name in names {
     print("Hello, \(name)!")
 }
```

**'while' left brace**

```diff
 var square = 0
 var diceRoll = 0
-while square < finalSquare{
+while square < finalSquare {
     // roll the dice
     diceRoll += 1
     if diceRoll == 7 { diceRoll = 1 }
```

**'do' left brace**

**'switch' left brace**

```diff
 let someCharacter: Character = "z"
-switch someCharacter{
+switch someCharacter {
 case "a":
     print("The first letter of the alphabet")
 case "z":
```

**'catch' left brace**

#### Before Keywords

**'else' keyword**

```diff
 temperatureInFahrenheit = 40
 if temperatureInFahrenheit <= 32 {
     print("It's very cold. Consider wearing a scarf.")
-}else {
+} else {
     print("It's not that cold. Wear a t-shirt.")
 }
```

**'while' keyword**

```diff
     if diceRoll == 7 { diceRoll = 1 }
     // move by the rolled amount
     square += diceRoll
-}while square < finalSquare
+} while square < finalSquare
 print("Game over!")
```

**'catch' keyword**

#### Within

**Code braces**

**Brackets**

`"brackets" : true`

**Array and dictionary literal brackets**

`"arrayAndDictionaryLiteralBrackets" : true`

```diff
-var shoppingList = ["Eggs", "Milk"]
-shoppingList += ["Baking Powder"]
-shoppingList += ["Chocolate Spread", "Cheese", "Butter"]
+var shoppingList = [ "Eggs", "Milk" ]
+shoppingList += [ "Baking Powder" ]
+shoppingList += [ "Chocolate Spread", "Cheese", "Butter" ]
```

**Grouping parenthesese**

**Method/function declaration parenthesese**

`"functionDeclarationParentheses" : true`

```diff
-func greet(person: String) -> String {
+func greet( person: String ) -> String {
     let greeting = "Hello, " + person + "!"
     return greeting
 }
```

**Empty method/function declaration parenthesese**

**Method/function call parenthesese**

**Empty method/function call parenthesese**

**'if' parenthesese**

**'while' parenthesese**

**'switch' parenthesese**

**'catch' parenthesese**

**Attribute parenthesese**

#### In Ternary Operator (:?)

**After '?'**

**Before ':'**

**After ':'**

#### Around colons

**Before colon in type annotations**

**After colon in type annotations**

**Before colon in type inheritance clauses**

**After colon in type inheritance clauses**

**Before colon in dictionary types**

**After colon in dictionary types**

**Before colon in dictionary literal 'key:value' pair**

**After colon in dictionary literal 'key:value' pair**

#### Within Type Arguments

**After comma**

#### Other

**Before comma**

**After comma**

**Before semicolon**

**After semicolon**

### Wrapping and Braces

### Blank Lines

#### Keep Maximum Blank Lines

**In declarations**

**In code**

**Before '}'**

#### Minimum Blank Lines

**Before imports**

`"beforeImports" : 1`

```diff
 //
 //  Created by Kishikawa Katsumi on 2018/02/14.
 //
+
 import Foundation
 import Basic
 import SwiftSyntax
```

**After imports**

`"afterImports" : 1`

```diff
 import Foundation
 import Basic
 import SwiftSyntax
+
 public struct Processor {
     private let options: [String]
```

**Around type declarations**

`"aroundTypeDeclarations" : 1`

```diff
@@ -9,6 +9,7 @@ fileprivate class Bracket : Indentation {
         self.lineNumber = lineNumber
     }
 }
+
 fileprivate class SwitchStatement {
     var lineNumber: Int
 
@@ -16,6 +17,7 @@ fileprivate class SwitchStatement {
         self.lineNumber = lineNumber
     }
 }
+
 fileprivate class CaseBranch {
     var lineNumber: Int
 
@@ -23,6 +25,7 @@ fileprivate class CaseBranch {
         self.lineNumber = lineNumber
     }
 }
+
 protocol Indentation {
     var indent: Bool { get set }
     var alignment: Int { get set }
```

**Around property in protocol**

`"aroundPropertyInProtocol" : 0`

**Around property**

`"aroundProperty" : 1`

**Around method/function in protocol**

`"aroundFunctionInProtocol" : 0`

**Around method/function**

`"aroundFunction" : 1`

**Before method/function body**

`"beforeFunctionBody" : 0`

Author
---------------------------------------
Kishikawa Katsumi, kishikawakatsumi@mac.com

License
---------------------------------------
Swiftfmt is available under the Apache 2.0 license. See the LICENSE file for more info.
