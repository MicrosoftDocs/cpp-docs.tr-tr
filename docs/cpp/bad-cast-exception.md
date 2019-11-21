---
title: bad_cast özel durumu
ms.date: 10/04/2019
f1_keywords:
- bad_cast
- bad_cast_cpp
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
ms.openlocfilehash: 11b42c9e6210c2432563bba43c55517abd4265fe
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245951"
---
# <a name="bad_cast-exception"></a>bad_cast özel durumu

The **bad_cast** exception is thrown by the **dynamic_cast** operator as the result of a failed cast to a reference type.

## <a name="syntax"></a>Sözdizimi

```
catch (bad_cast)
   statement
```

## <a name="remarks"></a>Açıklamalar

The interface for **bad_cast** is:

```cpp
class bad_cast : public exception
```

The following code contains an example of a failed **dynamic_cast** that throws the **bad_cast** exception.

```cpp
// expre_bad_cast_Exception.cpp
// compile with: /EHsc /GR
#include <typeinfo>
#include <iostream>

class Shape {
public:
   virtual void virtualfunc() const {}
};

class Circle: public Shape {
public:
   virtual void virtualfunc() const {}
};

using namespace std;
int main() {
   Shape shape_instance;
   Shape& ref_shape = shape_instance;
   try {
      Circle& ref_circle = dynamic_cast<Circle&>(ref_shape);
   }
   catch (bad_cast b) {
      cout << "Caught: " << b.what();
   }
}
```

The exception is thrown because the object being cast (a Shape) isn't derived from the specified cast type (Circle). Özel durumdan kaçınmak için bu bildirimleri `main` öğesine ekleyin:

```cpp
Circle circle_instance;
Circle& ref_circle = circle_instance;
```

Then reverse the sense of the cast in the **try** block as follows:

```cpp
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[bad_cast](#bad_cast)|The constructor for objects of type `bad_cast`.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[what](#what)|TBD|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|An assignment operator that assigns one `bad_cast` object to another.|

## <a name="bad_cast"></a> bad_cast

The constructor for objects of type `bad_cast`.

```cpp
bad_cast(const char * _Message = "bad cast");
bad_cast(const bad_cast &);
```

## <a name="op_eq"></a> operator=

An assignment operator that assigns one `bad_cast` object to another.

```cpp
bad_cast& operator=(const bad_cast&) noexcept;
```

## <a name="what"></a> what

```cpp
const char* what() const noexcept override;
```

## <a name="see-also"></a>Ayrıca bkz.

[dynamic_cast Operator](../cpp/dynamic-cast-operator.md)\
[Keywords](../cpp/keywords-cpp.md)\
[Modern C++ best practices for exceptions and error handling](../cpp/errors-and-exception-handling-modern-cpp.md)
