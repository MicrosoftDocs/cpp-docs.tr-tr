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

**Bad_cast** özel durumu, bir başvuru türüne başarısız bir dönüştürme sonucu olarak **dynamic_cast** işleci tarafından oluşturulur.

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

Aşağıdaki kod, **bad_cast** özel durumunu oluşturan başarısız **dynamic_cast** bir örnek içerir.

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

Sonra **TRY** bloğunda dönüştürmenin anlamlı olduğunu aşağıdaki gibi tersine çevirin:

```cpp
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);
```

## <a name="members"></a>Üyeleri

### <a name="constructors"></a>Oluşturucular

|Constructor|Açıklama|
|-|-|
|[bad_cast](#bad_cast)|`bad_cast`türündeki nesneler için Oluşturucu.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[Yazdırılacak](#what)|TBD|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Bir `bad_cast` nesnesini diğerine atayan atama işleci.|

## <a name="bad_cast"></a>bad_cast

`bad_cast`türündeki nesneler için Oluşturucu.

```cpp
bad_cast(const char * _Message = "bad cast");
bad_cast(const bad_cast &);
```

## <a name="op_eq"></a>işleç =

Bir `bad_cast` nesnesini diğerine atayan atama işleci.

```cpp
bad_cast& operator=(const bad_cast&) noexcept;
```

## <a name="what"></a>Yazdırılacak

```cpp
const char* what() const noexcept override;
```

## <a name="see-also"></a>Ayrıca bkz.

[dynamic_cast işleci](../cpp/dynamic-cast-operator.md)\
[Anahtar sözcükler](../cpp/keywords-cpp.md)\
[Özel C++ durumlar ve hata işleme için modern en iyi uygulamalar](../cpp/errors-and-exception-handling-modern-cpp.md)
