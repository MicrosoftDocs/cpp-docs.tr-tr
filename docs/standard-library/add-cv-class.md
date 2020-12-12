---
description: 'Hakkında daha fazla bilgi edinin: add_cv sınıfı'
title: add_cv Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_cv
helpviewer_keywords:
- add_cv class
- add_cv
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
ms.openlocfilehash: bc25efd879a27b3d3af2e5f4db8dd74fafa3fb45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319937"
---
# <a name="add_cv-class"></a>add_cv Sınıfı

Türden **`const volatile`** türü oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct add_cv;

template <class T>
using add_cv_t = typename add_cv<T>::type;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Değiştirilen türün örneği, t `add_cv<T>` `type` **`typedef`** zaten CV niteleyicilerine sahip olmadığı  , bir başvuru ya da bir işlev olduğu müddetçe  , hem [add_volatile](add-volatile-class.md) hem de [add_const](add-const-class.md)tarafından değiştirilmiş bir üyeye sahiptir.

`add_cv_t<T>`Yardımcı türü, typedef üyesine erişmek için bir kısayoldur `add_cv<T>` `type` .

## <a name="example"></a>Örnek

```cpp
// add_cv.cpp
// compile by using: cl /EHsc /W4 add_cv.cpp
#include <type_traits>
#include <iostream>

struct S {
    void f() {
        std::cout << "invoked non-cv-qualified S.f()" << std::endl;
    }
    void f() const {
        std::cout << "invoked const S.f()" << std::endl;
    }
    void f() volatile {
        std::cout << "invoked volatile S.f()" << std::endl;
    }
    void f() const volatile {
        std::cout << "invoked const volatile S.f()" << std::endl;
    }
};

template <class T>
void invoke() {
    T t;
    ((T *)&t)->f();
}

int main()
{
    invoke<S>();
    invoke<std::add_const<S>::type>();
    invoke<std::add_volatile<S>::type>();
    invoke<std::add_cv<S>::type>();
}
```

```Output
invoked non-cv-qualified S.f()
invoked const S.f()
invoked volatile S.f()
invoked const volatile S.f()
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](type-traits.md)\
[remove_const sınıfı](remove-const-class.md)\
[remove_volatile sınıfı](remove-volatile-class.md)
