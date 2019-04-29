---
title: Derleyici Hatası C2992
ms.date: 11/04/2016
f1_keywords:
- C2992
helpviewer_keywords:
- C2992
ms.assetid: 01b16447-43fe-4e91-9a5a-af884a166a31
ms.openlocfilehash: c30a1d2e1c2bae92b426fdd8fa4be628c009fa02
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366036"
---
# <a name="compiler-error-c2992"></a>Derleyici Hatası C2992

'class': geçersiz veya eksik tür parametresi listesi

Sınıf öncesinde bir `template` veya **genel** eksik veya geçersiz parametrelerle anahtar sözcüğü.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2992 oluşturur:

```
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