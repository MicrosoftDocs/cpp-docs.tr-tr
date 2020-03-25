---
title: Derleyici hatası C3771
ms.date: 11/04/2016
f1_keywords:
- C3771
helpviewer_keywords:
- C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
ms.openlocfilehash: 6c29ad6007d33c43ae1e4758ae05caa9109053e3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165736"
---
# <a name="compiler-error-c3771"></a>Derleyici hatası C3771

"tanımlayıcı": friend bildirimi en yakın ad alanı kapsamında bulunamıyor

Belirtilen şablon *tanımlayıcısı* için sınıf şablonu bildirimi geçerli ad alanı içinde bulunamıyor.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Şablon tanımlayıcısı için sınıf şablonu bildiriminin geçerli ad alanında tanımlandığından veya şablon tanımlayıcısının tam nitelikli bir ad olduğundan emin olun.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, ad alanı `NA`bir sınıf şablonu ve işlevi bildirir, ancak ad alanı `NB`bir arkadaş işlev şablonu bildirmeye çalışır.

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
