---
title: Derleyici Hatası C3740
ms.date: 11/04/2016
f1_keywords:
- C3740
helpviewer_keywords:
- C3740
ms.assetid: edb17a90-2307-4df6-943d-580460d26d2b
ms.openlocfilehash: dd493e4759b2fb70918bf94f14f4ada022e326b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547231"
---
# <a name="compiler-error-c3740"></a>Derleyici Hatası C3740

Şablon kaynağı veya olayları alma

Bir şablonlu sınıfın veya yapının içeremez [olayları](../../cpp/event-handling.md).

Aşağıdaki örnek, C3740 oluşturur:

```
// C3740.cpp
template <typename T>   // Delete the template specification
struct E {
   __event void f();   // C3740
};

int main() {
}
```