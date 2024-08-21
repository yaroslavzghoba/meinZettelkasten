# Об'єкти
Майже усі сутності в JavaScript є об'єктами. 
```js
const myObject = {
    property1: 'value1',
    property2: 'value2',
}
```
==Привласнуюючи об'єкт змінній, привласнюється посилання на об'єкт в пам'яті== Іншими словами, якщо ви модифікуєте об'єкт, це відобразиться на усіх змінних, які посилаються на даний об'єкт.
```js
// Edit exists property
myObject.propery2 = 0

// Add new property
myObject.property3 = 'value3'
myObject['property4'] = 'value4'

// Delete the propery
delete myObject.property3
delete myObject['property4']
```
Значеннями властивостивостей об'єкта можуть бути також функці та на інші об'єкти (посилання на них).
```js
const myObject2 = {
    method1: function () { },
    method2() { },
}

myObject2.method1()
myObject2.method2()
```
## JSON
```js
// Convert object to JSON
const json = JSON.stringify(myObject)

// Convert JSON to object
const parsedObject = JSON.parse(json)
```
## Мутація об'єктів
Як згадувалося раніше, передаючи значення змінної, яка містить посилання на об'єкт, іншій змінній, передається посилання на той самий об'єкт в пам'яті. Це дає можливість модифікувати об'єкт використовуючи з різні змінні. Щоб уникнути цього необхідно передавати не посилання на копію об'єкта.
```js
const copiedObject = JSON.parse(
	JSON.stringify(myObject)
)
```
# Фукнції 
В JavaScript можна передавати функції в параметрах іншої функції
```js
function printHi() {
    console.log("Hello!")
}

setTimeout(printHello, 1000)
```