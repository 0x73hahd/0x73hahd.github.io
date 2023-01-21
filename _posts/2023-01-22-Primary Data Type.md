---
layout: post
title: Primary Data Types in C/C++
date: 2023-01-22 12:00am
categories: [Programming, C++]
tags: [c/c++, data types]
---

<p dir="rtl" lang="ar">
لغة الـسي بلس بلس <a href="https://en.wikipedia.org/wiki/Strong_and_weak_typing">strongly-typed</a> language، يعني كل variable هـنعملو declaration لازم نحدد الـ data type بتعتو الأول، دا عشان نعرف الـ compiler بالحجم اللي هيحجزو ف الـ memory للـ variable، الحجم هيكون حسب الـ data type لأن كل data type بتاخد مساحة معينة فـ الـ memory، الـ data types فـ الـ ++C ليها أنواع اساسية(Primary)، مشتقة(Derived) و أنواع أحنا بنعملها(User Defined).
</p>


![C_C++_Data_Types](/pic/C_C++_Data_Types.png)

---

## 1.  Integer Types

<p dir="rtl" lang="ar">
لغة الـ ++C عندها أربعة أحجام للـ Integer، كل واحد من الأربعة ممكن يكون signed (سالب أو موجب أو صفر) أو unsigned (موجب بس)، للأختصار ممكن نكتب long بس بدل long int وكهذا..
</p>

![Int_in_cpp](/pic/Int_in_cpp.png)



### Sizes of Integer Types


![int_type_size](/pic/int_type_size.png)


### integer literal representations

representation|prefix
--------------|-------
binary        | 0b
octal         | 0
decimal       | The default
hexadecimal   | 0x

---

## 2. Floating-Point Types
<p dir="rtl" lang="ar">
الأرقام العشرية والجزء الكسري منها مش بيتخزن بشكل كامل فـ الـ Memory لكن بيتخزن بشكل تقريبي، الـ Floating-Point Types بتاخد جزء محدود من الـ Memory بيسمى بـ type’s <a href="https://en.wikipedia.org/wiki/Precision_(computer_science)">precision</a>، لغة الـ ++C ليها ثلاث مستويات precision:
</p>

   -  **float** -> single precision.
   - **double** -> double precision.
   - **long double** -> extended precision.

### Floating-Point Literals
<p dir="rtl" lang="ar">
الـ default للـ Floating-point <a href="https://en.wikipedia.org/wiki/Literal_(computer_programming">literals</a> هو double precision، لو عايزين الـ single precision بنستخدم الـخاتمة (suffix) f أو F، و للـ extended precision بنستخدم l أو L كـ suffix.
</p>

```cpp
float single_precision = 0.96F; // for single precision
double double_precision = 0.256; // for double precision
long double extended_precision = 0.85L; // for extended precision
```
<p dir="rtl" lang="ar">
ممكن نستخم الـ Scientific notation فـ الـ Floating-point literals
</p>

```cpp
double avogadro_const = 6.022e23; // = 6.02 x 10^23 (positive exponent)
double electron_charge = 1.6e-19; // = 1.6 x 10^-19 (negative exponent)

```

### float vs. double

<p dir="rtl" lang="ar">
طب ايه الفرق بين float و double ؟
</p>

Difference |float   | double  |
--------|---------|-------------
[IEEE 754](https://en.wikipedia.org/wiki/IEEE_754)|single-precision|double-precision|
occupy |32 bits |64 bits  |
Byte Size|4 byte | 8 byte |
precision after decimal point| 7 decimal digits | 15 decimal digits

- ### float is a 32-bit IEEE 754 single precision


![single-precision](/pic/single-precision.png)



- ### double is a 64-bit IEEE 754 double precision

![double-precision](/pic/double-precision.png)

---

## 3. Booleans
<p dir="rtl" lang="ar">
الـ Boolean values اتنين بس true أو false، رقم 1 أو اي قيمة غير الصفر بتمثل true، الـ 0 بيمثل false
</p>

```cpp
bool i_love_u = true
bool i_hate_u = false
```
```cpp
// Do you want to watch a movie with me? 
bool answer = 0; // This means false
if(answer)
    std::cout << "Okay let's watch, I love you <3"; // case answer is true or any number except 0
else
    std::cout << ".. stupid I'll eat all the popcorn alone 💢"; // case answer is false or 0
```

---

## 4. Character Types

<p dir="rtl" lang="ar">
الـ Character Types بتخزن اي رموز و حروف، وفي ستة أنواع للـ Character Types:
</p>

Character Types | character sets
----------------|---------------
char            |     1-byte    
char16_t        |     2-byte    
char32_t        |     4-byte    
signed char     |     1-byte    
unsigned char   |     1-byte
wchar_t         |support the largest character sets


<p dir="rtl" lang="ar">
ايه الاختلاف بين signed char و unsigned char ؟
</p>

The difference | signed char | unsigned char
---------------|-------------|--------------
  Range        | -128 to 127 | 0 to 255
  Data bits    |  7 data bits (1 for the sign)   | 8 bits for data

- ### signed char

![signed_char](/pic/signed_char.png)

- ### unsigned char

![unsigned_char](/pic/unsigned_char.png)

---
## 5. void
<p dir="rtl" lang="ar">
بنستخدم void فـ حالة أن الدالة مبترجعش أي value 
</p>

```cpp
// It just print some text and doesn't return any value
void I_dont_return(){
    std::cout << "I don't return any value.";
}

// void function مثال عكس الـ
int I_return_int_value(){
    int x = 2; int y = 8;
    int sum = x + y;
    return sum; // In this case return value is 10
}
```
