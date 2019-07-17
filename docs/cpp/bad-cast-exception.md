---
title: bad_cast Özel Durumu
ms.date: 11/04/2016
f1_keywords:
- bad_cast
- bad_cast_cpp
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
ms.openlocfilehash: b40f64671e7c259b7dc04b31a11d20d0fc76c5c4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68242391"
---
# <a name="badcast-exception"></a>bad_cast Özel Durumu

**Bad_cast** tarafından özel durum **dynamic_cast** işleci bir başvuru türüne yapılan başarısız atamanın sonucu olarak.

## <a name="syntax"></a>Sözdizimi

```
catch (bad_cast)
   statement
```

## <a name="remarks"></a>Açıklamalar

Arabirimin **bad_cast** olan:

```cpp
class bad_cast : public exception
```

Başarısız bir örneği aşağıdaki kodu içeren **dynamic_cast** oluşturan **bad_cast** özel durum.

```cpp
// expre_bad_cast_Exception.cpp
// compile with: /EHsc /GR
#include <typeinfo.h>
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

Özel durum, atanan nesne (bir Şekil) belirtilen atama türünden (Daire) türetilmediği için oluşturulur. Özel durumdan kaçınmak için bu bildirimleri `main` öğesine ekleyin:

```cpp
Circle circle_instance;
Circle& ref_circle = circle_instance;
```

Ardından algılama atama yönünü ters **deneyin** bloğunu şu şekilde:

```cpp
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[bad_cast](#bad_cast)|Türündeki nesneler için oluşturucu `bad_cast`.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[ne](#what)|TBD|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Atar bir atama işleci `bad_cast` başka bir nesne.|

## <a name="bad_cast"></a> bad_cast

Türündeki nesneler için oluşturucu `bad_cast`.

```cpp
bad_cast(const char * _Message = "bad cast");
bad_cast(const bad_cast &);
```

## <a name="op_eq"></a> işleç =

Atar bir atama işleci `bad_cast` başka bir nesne.

```cpp
bad_cast& operator=(const bad_cast&) noexcept;
```

## <a name="what"></a> ne

```cpp
const char* what() const noexcept override;
```

## <a name="see-also"></a>Ayrıca bkz.

[dynamic_cast İşleci](../cpp/dynamic-cast-operator.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)