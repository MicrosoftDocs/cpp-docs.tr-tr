---
title: add_cv Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_cv
helpviewer_keywords:
- add_cv class
- add_cv
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
ms.openlocfilehash: 0cc63558ea392976bd6a3c5a43735c592e4606b4
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456590"
---
# <a name="addcv-class"></a>add_cv Sınıfı

Türünden **const geçici** tür yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct add_cv;

template <class T>
using add_cv_t = typename add_cv<T>::type;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Değiştirilen türün `add_cv<T>` bir örneği, *t* zaten CV niteleyicilerine sahip olmadığı, bir başvuru veya bir değer olduğu müddetçe, hem [add_volatile](../standard-library/add-volatile-class.md) hem de [add_const](../standard-library/add-const-class.md)tarafından değiştirilen bir `type` üye **typedef** *öğesine sahiptir* . çalışmayacaktır.

Yardımcı türü, typedef `add_cv<T>` `type`üyesine erişmek için bir kısayoldur. `add_cv_t<T>`

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

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[remove_const sınıfı](../standard-library/remove-const-class.md)\
[remove_volatile Sınıfı](../standard-library/remove-volatile-class.md)
