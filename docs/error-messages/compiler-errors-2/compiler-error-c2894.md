---
title: Derleyici Hatası C2894
ms.date: 11/04/2016
f1_keywords:
- C2894
helpviewer_keywords:
- C2894
ms.assetid: 4e250579-2b59-4993-a6f4-49273e7ecf06
ms.openlocfilehash: 4184f6360e36a4e8ca0cfc55dc6d9c515cf655d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494607"
---
# <a name="compiler-error-c2894"></a>Derleyici Hatası C2894

Şablonlar 'C' bağlaması olacak şekilde bildirilemez

Bu hata içinde tanımlanmış bir şablon neden olabilir bir `extern` "C" blok.

Aşağıdaki örnek, C2894 oluşturur:

```
// C2894.cpp
extern "C" {
   template<class T> class stack {};   // C2894 fail

   template<class T> void f(const T &aT) {}   // C2894
}
```

Aşağıdaki örnek, C2894 oluşturur:

```
// C2894b.cpp
// compile with: /c
extern "C" template<class T> void f(const T &aT) {}   // C2894

template<class T> void f2(const T &aT) {}   // OK
```