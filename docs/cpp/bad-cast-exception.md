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
ms.openlocfilehash: 028fa8cc90b33aca6a37fb3b7f58b8c5fad81bd7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573359"
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
class bad_cast : public exception {
public:
   bad_cast(const char * _Message = "bad cast");
   bad_cast(const bad_cast &);
   virtual ~bad_cast();
};
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

## <a name="see-also"></a>Ayrıca bkz.

[dynamic_cast İşleci](../cpp/dynamic-cast-operator.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)