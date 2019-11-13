---
title: Derleyici Uyarısı (düzey 1) C4544
ms.date: 11/04/2016
f1_keywords:
- C4544
helpviewer_keywords:
- C4544
ms.assetid: 11ee04df-41ae-435f-af44-881e801315a8
ms.openlocfilehash: 094662270569c7362b7bb3c4953a466b19ed2e65
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966480"
---
# <a name="compiler-warning-level-1-c4544"></a>Derleyici Uyarısı (düzey 1) C4544

' declaration ': varsayılan şablon bağımsız değişkeni bu şablon bildiriminde yoksayıldı

Varsayılan şablon bağımsız değişkeni yanlış bir konumda belirtildi ve yoksayıldı. Sınıf şablonu için varsayılan bir şablon bağımsız değişkeni, sınıf şablonunun bir üyesi üzerinde değil, yalnızca sınıf şablonunun bildiriminde veya tanımında belirtilebilir.

Bu örnek C4545 oluşturur ve sonraki örnek bunun nasıl düzeltileceğini göstermektedir:

```cpp
// C4544.cpp
// compile with: /W1 /LD
template <class T>
struct S
{
   template <class T1>
      struct S1;
   void f();
};

template <class T=int>
template <class T1>
struct S<T>::S1 {};   // C4544
```

Bu örnekte, varsayılan parametre `S`sınıf şablonu için geçerlidir:

```cpp
// C4544b.cpp
// compile with: /LD
template <class T = int>
struct S
{
   template <class T1>
      struct S1;
   void f();
};

template <class T>
template <class T1>
struct S<T>::S1 {};
```