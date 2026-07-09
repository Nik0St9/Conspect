# Конспект по теме «DOM-события»

## Основы DOM-событий

DOM-события --- это механизм взаимодействия JavaScript с веб-страницей.
Событием считается любое действие пользователя или браузера, например
клик мышью, ввод текста, отправка формы, нажатие клавиши или загрузка
документа. JavaScript позволяет отслеживать эти действия и выполнять
определенный код в ответ на них.

## addEventListener()

Метод `addEventListener()` используется для регистрации обработчика
события. Он принимает название события и функцию, которая будет
выполнена при его возникновении.

``` javascript
const button=document.querySelector("button");
button.addEventListener("click",()=>console.log("Клик"));
```

## Объект Event

При возникновении события браузер создает объект `Event`, содержащий
сведения о событии.

``` javascript
button.addEventListener("click",(event)=>{
  console.log(event.type);
});
```

## target / currentTarget

`target` --- элемент, на котором произошло событие. `currentTarget` ---
элемент, на котором установлен обработчик.

``` javascript
list.addEventListener("click",(event)=>{
  console.log(event.target);
  console.log(event.currentTarget);
});
```

## click

Событие `click` возникает после нажатия кнопкой мыши.

``` javascript
button.addEventListener("click",()=>alert("Привет"));
```

## input

Событие `input` возникает при каждом изменении поля.

``` javascript
input.addEventListener("input",()=>console.log(input.value));
```

## change

Событие `change` происходит после завершения изменения значения.

``` javascript
input.addEventListener("change",()=>console.log(input.value));
```

## submit

Используется при отправке формы.

``` javascript
form.addEventListener("submit",(event)=>{
  event.preventDefault();
});
```

## preventDefault()

Отменяет стандартное действие браузера.

``` javascript
event.preventDefault();
```

## stopPropagation()

Останавливает всплытие события.

``` javascript
event.stopPropagation();
```

## keydown

Срабатывает при нажатии клавиши.

``` javascript
document.addEventListener("keydown",(event)=>console.log(event.key));
```

## focus / blur

Используются при получении и потере фокуса.

``` javascript
input.addEventListener("focus",()=>{});
input.addEventListener("blur",()=>{});
```

## Bubbling (всплытие)

Всплытие --- передача события от дочернего элемента к его родителям.
Этот механизм лежит в основе делегирования событий.

## Делегирование событий

Один обработчик назначается общему родителю нескольких элементов.

``` javascript
list.addEventListener("click",(event)=>{
 if(event.target.tagName==="LI"){
   console.log(event.target.textContent);
 }
});
```

## closest()

Метод ищет ближайшего родителя по CSS-селектору.

``` javascript
const item=event.target.closest("li");
```

## data-\* атрибуты

Позволяют хранить пользовательские данные в HTML.

``` html
<button data-id="15">Удалить</button>
```

``` javascript
console.log(button.dataset.id);
```

## DOMContentLoaded

Срабатывает после полной загрузки HTML-документа.

``` javascript
document.addEventListener("DOMContentLoaded",()=>{});
```

## Debounce для input

Debounce уменьшает количество вызовов функции при быстром вводе.

``` javascript
function debounce(fn,delay){
 let t;
 return ()=>{clearTimeout(t);t=setTimeout(fn,delay);}
}
```

## removeEventListener()

Удаляет ранее зарегистрированный обработчик.

``` javascript
button.removeEventListener("click",handler);
```

## async/await в обработчиках

Обработчики могут быть асинхронными.

``` javascript
button.addEventListener("click",async()=>{
 const res=await fetch("/users");
});
```

## Обработка динамически созданных элементов

Для новых элементов обычно используют делегирование.

``` javascript
document.addEventListener("click",(event)=>{
 if(event.target.matches(".delete")){
   console.log("Удаление");
 }
});
```

## Валидация форм через события

Проверка выполняется до отправки формы.

``` javascript
if(input.value===""){
 event.preventDefault();
}
```

## mouseenter / mouseleave

Используются при наведении и уходе курсора.

``` javascript
box.addEventListener("mouseenter",()=>{});
box.addEventListener("mouseleave",()=>{});
```

## Scroll events

Событие возникает при прокрутке страницы.

``` javascript
window.addEventListener("scroll",()=>{
 console.log(window.scrollY);
});
```

## this и стрелочные функции в обработчиках

В обычной функции `this` указывает на элемент с обработчиком. В
стрелочных функциях рекомендуется использовать `event.currentTarget`.

``` javascript
button.addEventListener("click",function(){
 console.log(this);
});
```
