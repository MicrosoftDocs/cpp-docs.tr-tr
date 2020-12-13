---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2992'
title: Derleyici hatası C2992
ms.date: 11/04/2016
f1_keywords:
- C2992
helpviewer_keywords:
- C2992
ms.assetid: 01b16447-43fe-4e91-9a5a-af884a166a31
ms.openlocfilehash: b96ca202ee3d8128e3cbd27e4e114519f625aaf9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338620"
---
# <a name="compiler-error-c2992"></a>Derleyici hatası C2992

' class ': geçersiz veya eksik tür parametresi listesi

Sınıfı, **`template`** eksik veya geçersiz parametrelere sahip bir veya **genel** anahtar kelimedir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2992 oluşturur:

```cpp
// C2992.cpp
// compile with: /c
template <class T>
struct TC1 {
   template <class U>
   struct TC2;
};

template <class T>   struct TC1<T>::TC2 {};   // C2992

// OK
template <class T>
template <class U>
struct TC1<T>::TC2 {};
// C2992 can also occur when using generics:
// C2992c.cpp
// compile with: /clr /c
generic <class T>
ref struct GC1 {
   generic <class U>
   ref struct GC2;
};

generic <class T> ref struct GC1<T>::GC2 {};   // C2992

// OK
generic <class T>
generic <class U>
ref struct GC1<T>::GC2 {};
```
