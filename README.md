---
### JavaScript Best Practice Guide
---

__1. ������� ���������� ����������.__

����� � �������� ������������� ���������� ���������� ���� �� ��� ���� ������, ������� ��� �������. ���������� ���������� ����� ���� ������������ ������� ���������!
```
//�����
let firstNum = 4;
let secondNum = 9;

let sum = () => {
  firstNum + secondNum;
}

//������
let sum = () => {
  let firstNum = 4;
  let secondNum = 9;
  firstNum + secondNum;
}
```
__2. ����������� ����� ����� � �������.__

������ ����������� ������ ���������� ������ � �������. � ��������� ������� ������� ����� � ������� �������� ����������, ����� �� �������� ��������� � �������������� ������. ������:
```
function returnPerson (name) {
  return //JS ������������� �������� ����� � ������� �����
  {
    name : name
  };
}
```
```
//�����
let luke = {}
let leia = {}

[luke, leia].forEach((jedi) => {
  jedi.father = 'vader';
})

// ������
let luke = {};
let leia = {};

[luke, leia].forEach((jedi) => {
  jedi.father = 'vader';
});
```

__3. ���������  ��������������� �������������� �����.__

JavaScript �������� ����� ��������������. ������� �������������� ����� �������� � ����������� �����������.
```
//�����
let x = 5 + "7";  // x.valueOf() is 57,  typeof x is a string

//������
let x = 5 + 7;  // x.valueOf() is 12,  typeof x is a number
```

__4. ��������� === � !== ������ == � !=.__

��������� ��������� == � != ������ ����������� ���� ������ � ��������������� ���� ����� ����������. ������� �������������� ����� ����� �������� � ���������� ������� � ����.
```
//�����
1 == '1'; //true
0 == ' '; //true

//������
1 === '1'; //false
0 === ' '; //false
```

__5. �� ����������� new Object(), new Array().__

�� ���������� ������� � ������� ����� ������������ new Oject � new Array ��������������. ��� ��������, ����� ����� ������������ ������� ���������� ����.
```
// �����
let items = new Array();
let items = new Object();

// ������
let items = [];
let items = {};
```

__6. ��������������� ���������� ��� �� ����������.__

��� ������� �������� �������������� ��������.
```
//�����
let name;
let age;

name = 'Ksu';
age = 25;

//������
let name = 'Ksu';
let age = 25;
```

__7. ������������� �������� ������.__

������ ��������� �������� ������. ������������ ��� ����� �������� ������������� ������ ��� � ������������ ����������. ��������������� ������ ����� �������� � ������������ ������ ����.
```
//�����
if(someVariableExists)  
  x = false

//������
if(2 + 2 === 4) return 'nicely done';

if(someVariableExists) {  
  x = false;  
  anotherFunctionCall();  
}
```
__8. ���������� ���������� ��� 'for" ��� ������.__

����� ���������� ������ ���� �for� �� ����������� ������ ������ ������ ������ ��� �����.

```
//�����
for(var i = 0; i < someArray.length; i++) {  
  var container = document.getElementById('container');  
  container.innerHtml += 'my number: ' + i;  
  console.log(i);  
}  

//������
var container = document.getElementById('container');  

for(var i = 0, len = someArray.length; i < len;  i++) {  
  container.innerHtml += 'my number: ' + i;  
  console.log(i);  
}  
```
__9. ������ ���������� switch � default.__

��� �������� ������� � ������ ������, ���� ��� ��������.

```
//�����
switch (new Date().getDay()) {
  case 0:
    day = "Sunday";
    break;
  case 1:
    day = "Monday";
    break;
  case 2:
    day = "Tuesday";
    break;
}

//������
switch (new Date().getDay()) {
  case 0:
    day = "Sunday";
    break;
  case 1:
    day = "Monday";
    break;
  case 2:
    day = "Tuesday";
    break;
  default:
    day = "Unknown";
}
```
__10. ��������� ������������� eval().__

������� eval() ��������� ��������� ������� ���������� � ��������� ����������, ������� ���������� � �������� ��������� � eval.

��� �������� ��������� , � ����� ������������ ������������� �������� ���� ������������ ����������.
```
//�����
eval( "�onsole.log('hello!');" );

//������
�onsole.log('hello!');  //����� ������ �������� ��������������� ���
```