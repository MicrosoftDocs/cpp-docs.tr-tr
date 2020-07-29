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
ms.openlocfilehash: 2efe5be5e44751831a56b29cfc629df2d21843f7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229187"
---
# <a name="bad_cast-exception"></a>bad_cast özel durumu

**Bad_cast** özel durumu, bir **`dynamic_cast`** başvuru türüne başarısız bir dönüştürme sonucu olarak işleç tarafından oluşturulur.

## <a name="syntax"></a>Sözdizimi

```
catch (bad_cast)
   statement
```

## <a name="remarks"></a>Açıklamalar

**Bad_cast** arabirimi:

```cpp
class bad_cast : public exception
```

Aşağıdaki kod, **`dynamic_cast`** **bad_cast** özel durumunu oluşturan başarısız bir örneği içerir.

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

Cast (bir şekil) nesne belirtilen atama türünden (Daire) türetilmediğinden özel durum oluşturuldu. Özel durumdan kaçınmak için bu bildirimleri `main` öğesine ekleyin:

```cpp
Circle circle_instance;
Circle& ref_circle = circle_instance;
```

Sonra, bloktaki dönüştürme türünü aşağıdaki gibi tersine çevirin **`try`** :

```cpp
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[bad_cast](#bad_cast)|Türündeki nesneler için Oluşturucu `bad_cast` .|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[Yazdırılacak](#what)|TBD|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Bir nesneyi diğerine atayan atama işleci `bad_cast` .|

## <a name="bad_cast"></a><a name="bad_cast"></a>bad_cast

Türündeki nesneler için Oluşturucu `bad_cast` .

```cpp
bad_cast(const char * _Message = "bad cast");
bad_cast(const bad_cast &);
```

## <a name="operator"></a><a name="op_eq"></a>işleç =

Bir nesneyi diğerine atayan atama işleci `bad_cast` .

```cpp
bad_cast& operator=(const bad_cast&) noexcept;
```

## <a name="what"></a><a name="what"></a>Yazdırılacak

```cpp
const char* what() const noexcept override;
```

## <a name="see-also"></a>Ayrıca bkz.

[dynamic_cast Işleci](../cpp/dynamic-cast-operator.md)\
[Lerimi](../cpp/keywords-cpp.md)\
[Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](../cpp/errors-and-exception-handling-modern-cpp.md)
