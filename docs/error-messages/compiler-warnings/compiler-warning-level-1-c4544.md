---
title: Derleyici Uyarısı (düzey 1) C4544
ms.date: 11/04/2016
f1_keywords:
- C4544
helpviewer_keywords:
- C4544
ms.assetid: 11ee04df-41ae-435f-af44-881e801315a8
ms.openlocfilehash: f2a3f2e64a6a859add8182de4fc883c735563e92
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532905"
---
# <a name="compiler-warning-level-1-c4544"></a>Derleyici Uyarısı (düzey 1) C4544

'bildirim': varsayılan şablon bağımsız değişkeni bu şablon bildiriminde yok sayıldı

Varsayılan şablon bağımsız değişkeni yanlış bir konumda belirtildi ve yoksayıldı. Bir sınıf şablonu için varsayılan şablon bağımsız değişkeni yalnızca bildirim veya tanımdan sınıf şablonunun ve değil, sınıf şablonunun üyesi belirtilebilir.

Bu örnek C4545 oluşturur ve sonraki örnek bu sorunun nasıl gösterir:

```
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

Bu örnekte, varsayılan parametre sınıf şablonu için geçerlidir. `S`:

```
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