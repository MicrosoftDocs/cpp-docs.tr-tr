---
title: Derleyici Hatası C2908
ms.date: 11/04/2016
f1_keywords:
- C2908
helpviewer_keywords:
- C2908
ms.assetid: 49cd2a21-cad8-4ba0-9a0b-3a0190d9344c
ms.openlocfilehash: f798be5ef93eb3f072036888b800fa4008fa2de9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460833"
---
# <a name="compiler-error-c2908"></a>Derleyici Hatası C2908

Açık özelleştirme; 'şablon' zaten başlatıldı

Birincil şablonunun bir özelleştirmesi açık uzmanlığında önce gerçekleşir.

Aşağıdaki örnek, C2908 oluşturur:

```
// C2908.cpp
// compile with: /c
template<class T> class X {};

void f() {
X<int> x;   //specialization and instantiation
            //of X<int>
}

template<> class X<int> {}  // C2908, explicit specialization
```