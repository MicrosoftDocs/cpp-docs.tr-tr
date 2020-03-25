---
title: Derleyici Uyarısı (düzey 1) C4544
ms.date: 11/04/2016
f1_keywords:
- C4544
helpviewer_keywords:
- C4544
ms.assetid: 11ee04df-41ae-435f-af44-881e801315a8
ms.openlocfilehash: 6aee8ba6b07e02f012755f609d8a5089cea280b1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186289"
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
