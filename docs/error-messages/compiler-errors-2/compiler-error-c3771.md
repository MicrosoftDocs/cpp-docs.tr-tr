---
title: Derleyici Hatası C3771
ms.date: 11/04/2016
f1_keywords:
- C3771
helpviewer_keywords:
- C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
ms.openlocfilehash: 6b15d867bbaf66f511cbda200d692f5db4371ab3
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026714"
---
# <a name="compiler-error-c3771"></a>Derleyici Hatası C3771

"tanımlayıcı": friend bildirimi en yakın ad alanı kapsamında bulunamıyor

Belirtilen şablonu için sınıf şablonu bildirimi *tanımlayıcı* geçerli ad alanı içinde bulunamıyor.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Sınıf şablonu bildirimi şablon tanımlayıcısı için geçerli bir ad alanında tanımlanır veya şablon tanımlayıcısı bir tam ad olduğundan emin olun.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, bir sınıf şablonu ve ad alanındaki işlevi bildirir `NA`, ancak ad alanında bir arkadaş işlev şablonu bildirmeye `NB`.

```cpp
// C3771.cpp
// compile with: /c

namespace NA {
template<class T> class A {
    void aFunction(T t) {};
    };
}
// using namespace NA;
namespace NB {
    class X {
        template<class T> friend void A<T>::aFunction(T); // C3771
// try the following line instead
//      template<class T> friend void NA::A<T>::aFunction(T);
// or try "using namespace NA;" instead.
    };
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Şablonlar](../../cpp/templates-cpp.md)