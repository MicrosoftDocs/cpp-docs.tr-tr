---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2264'
title: Derleyici hatası C2264
ms.date: 11/04/2016
f1_keywords:
- C2264
helpviewer_keywords:
- C2264
ms.assetid: 158b72cc-cee9-4a08-bd79-b7a5955345a8
ms.openlocfilehash: a838271897db7a1ce553e6e9ea0d3f3e0c985a9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328418"
---
# <a name="compiler-error-c2264"></a>Derleyici hatası C2264

' function ': işlev tanımında veya bildiriminde hata; işlev çağrılmadı

Yanlış bir tanım veya bildirim nedeniyle işlev çağrılamaz.

Aşağıdaki örnek C2264 oluşturur:

```cpp
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
