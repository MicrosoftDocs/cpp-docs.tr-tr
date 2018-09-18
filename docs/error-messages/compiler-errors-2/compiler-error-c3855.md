---
title: Derleyici Hatası C3855 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3855
dev_langs:
- C++
helpviewer_keywords:
- C3855
ms.assetid: ed90f8c0-4154-4243-b066-493913df5727
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccedf71e5560d3907338d2b0372030c13aeeb0c0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081240"
---
# <a name="compiler-error-c3855"></a>Derleyici Hatası C3855

'class': tür parametresi 'param' bildirimle uyumsuz

Derleyici, tür olmayan şablon veya farklı adlara sahip genel parametreler bulundu. Şablon uzmanlığı tanımında belirtilen şablon parametresi, bildirimle uyumsuz olduğunda bu durum oluşabilir.

Aşağıdaki örnek, C3855 oluşturur:

```
// C3855.cpp
template <int N>
struct C {
   void f();
};

template <char N>
void C<N>::f() {}   // C3855
```

Olası çözüm:

```
// C3855b.cpp
// compile with: /c
template <int N>
struct C {
   void f();
};

template <int N>
void C<N>::f() {}
```

C3855, genel türler kullanırken da meydana gelebilir:

```
// C3855c.cpp
// compile with: /clr
generic <class T>
ref struct GC1 {
   generic <class U>
   ref struct GC2;
};

generic <class T>
generic <class U>
generic <class V>
ref struct GC1<T>::GC2 { };   // C3855
```

Olası çözüm:

```
// C3855d.cpp
// compile with: /clr /c
generic <class T>
ref struct GC1 {
   generic <class U>
   ref struct GC2;
};

generic <class T>
generic <class U>
ref struct GC1<T>::GC2 { };
```