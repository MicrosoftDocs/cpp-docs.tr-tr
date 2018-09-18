---
title: Derleyici Hatası C2990 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2990
dev_langs:
- C++
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0afceb82a58ee5c0a21e39fcaf4ba0a9ee9f2c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066979"
---
# <a name="compiler-error-c2990"></a>Derleyici Hatası C2990

'class': sınıf olmayan türü olarak zaten bir sınıf türü olarak bildirilmiş

Olmayan genel veya Şablon sınıfı bir genel veya Şablon sınıfı yeniden tanımlar. Çakışmaları için üst bilgi dosyaları denetleyin.

Aşağıdaki örnek, C2990 oluşturur:

```
// C2990.cpp
// compile with: /c
template <class T>
class C{};
class C{};   // C2990
```

C2990, genel türler kullanırken da meydana gelebilir:

```
// C2990b.cpp
// compile with: /clr /c
generic <class T>
ref struct GC;

ref struct GC {};   // C2990
```

C2990 da Visual C++ derleyicisi, bir değişiklik nedeniyle Visual C++ 2005 oluşabilir; Derleyici, şimdi aynı türü için birden fazla bildirimi şablonu belirtimine göre aynı olmasını gerektirir.

Aşağıdaki örnek, C2990 oluşturur:

```
// C2990c.cpp
// compile with: /c
template<class T>
class A;

template<class T>
struct A2 {
   friend class A;   // C2990
};

// OK
template<class T>
struct B {
   template<class T>
   friend class A;
};
```