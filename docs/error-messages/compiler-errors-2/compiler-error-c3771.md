---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3771'
title: Derleyici hatası C3771
ms.date: 11/04/2016
f1_keywords:
- C3771
helpviewer_keywords:
- C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
ms.openlocfilehash: f7d71952411632ded02bc5121c6f6668eddeabc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291668"
---
# <a name="compiler-error-c3771"></a>Derleyici hatası C3771

"tanımlayıcı": friend bildirimi en yakın ad alanı kapsamında bulunamıyor

Belirtilen şablon *tanımlayıcısı* için sınıf şablonu bildirimi geçerli ad alanı içinde bulunamıyor.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Şablon tanımlayıcısı için sınıf şablonu bildiriminin geçerli ad alanında tanımlandığından veya şablon tanımlayıcısının tam nitelikli bir ad olduğundan emin olun.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, ad alanında bir sınıf şablonu ve işlevi bildirir `NA` , ancak ad alanında bir arkadaş işlev şablonu bildirmeye çalışır `NB` .

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
