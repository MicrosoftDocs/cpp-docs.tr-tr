---
title: Derleyici Hatası C2264
ms.date: 11/04/2016
f1_keywords:
- C2264
helpviewer_keywords:
- C2264
ms.assetid: 158b72cc-cee9-4a08-bd79-b7a5955345a8
ms.openlocfilehash: 65f8dc1f6f1ad8514b2a6bda1bbd9645af5c251a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667408"
---
# <a name="compiler-error-c2264"></a>Derleyici Hatası C2264

'function': işlev tanımında veya bildiriminde hata işlev çağrılmadı

İşlevi, bir tanım geçersiz veya bildirimi nedeniyle çağrılamaz.

Aşağıdaki örnek, C2264 oluşturur:

```
// C2264.cpp
struct C {
   // Delete the following line to resolve.
   operator int(int = 0){}   // incorrect declaration
};

struct D {
   operator int(){return 0;}   // OK
};

int main() {
   int i;

   C c;
   i = c;   // C2264

   D d;
   i = d;   // OK
}
```