---
title: Derleyici Uyarısı (düzey 1) C4544 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4544
dev_langs:
- C++
helpviewer_keywords:
- C4544
ms.assetid: 11ee04df-41ae-435f-af44-881e801315a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c7cd274f0d1b595d374e1b108db40a51395b968
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084282"
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