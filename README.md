# Информациска Безбедност - Лабораториска Вежба 2

## Функционалности

### **Регистрација**
- Корисникот внесува податоци: корисничко име, е-пошта и лозинка.
- Лозинката се хашира со помош на `CryptoJS` пред зачувување.
- Системот генерира 6-цифрен верификациски код.

### **Најава**
- Корисникот внесува е-пошта, лозинка и верификациски код.
- Системот проверува дали лозинката и кодот се точни.

### **Зачувување на податоци**
- Сите податоци (корисничко име, е-пошта, хаширана лозинка и код) се зачувуваат локално во `localStorage`.

### **Успешна најава**
- Доколку сите податоци се точни, корисникот е пренасочен на страната со порака „Добредојде“.

---

## Изглед на апликацијата

### **Регистрација**
Корисникот внесува податоци и добива верификациски код.

### **Најава**
Корисникот внесува е-пошта, лозинка и верификациски код.

### **Неуспешна најава**
Кога податоците не се точни, корисникот добива порака за грешка.

### **Успешна најава**
Корисникот е пренасочен на страницата „Добредојде на страната“.

---

## Како да се користи

### **1. Регистрација**
1. Отворете ја датотеката `register.html` во вашиот прелистувач.
2. Внесете корисничко име, е-пошта и лозинка.
3. Кодот за верификација ќе биде генериран и зачуван.
4. Запишете го кодот за да го користите при најава.

### **2. Најава**
1. Отворете ја датотеката `login.html` во вашиот прелистувач.
2. Внесете ја е-поштата и лозинката што ги користевте при регистрација.
3. Внесете го генерираниот верификациски код.
4. Ако податоците се точни, ќе бидете пренасочени на `success.html`.

---

## Технички детали

### **Технологии**
- **HTML**: За структурата на страниците.
- **CSS**: За стилизирање на корисничкиот интерфејс.
- **JavaScript**: За логиката на апликацијата.
- **CryptoJS**: За хаширање на лозинки.

### **Структура на проектот**
- `register.html`: Страница за регистрација.
- `login.html`: Страница за најава.
- `success.html`: Страница за успешно најавување.

---

## Функционализација

### **Чување податоци**
Податоците се зачувуваат во `localStorage` во следниот формат:
```
{
  "username": "Име",
  "password": "Хаширана лозинка",
  "verificationCode": "123456",
  "verified": false
}
```
### Генерирање и зачувување на кориснички податоци
```
localStorage.setItem(email, JSON.stringify({
  username,
  password: hashedPassword,
  verificationCode,
  verified: false
}));
```
### Проверка на верификациски код
```
if (user.verificationCode !== code) {
  alert("Невалиден код за верификација!");
  return;
}
```