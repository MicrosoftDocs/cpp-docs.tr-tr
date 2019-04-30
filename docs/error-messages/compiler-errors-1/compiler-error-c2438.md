---
title: Derleyici Hatası C2438
ms.date: 11/04/2016
f1_keywords:
- C2438
helpviewer_keywords:
- C2438
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
ms.openlocfilehash: b2861090b5f7629c7f0cd94ea38a99e888909258
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375762"
---
# <a name="compiler-error-c2438"></a>Derleyici Hatası C2438

'identifier': statik sınıf verileri Oluşturucu başlatılamıyor

Bir oluşturucu, bir sınıfın statik bir üye başlatmak için kullanılır. Statik üyeleri sınıf bildirimi dışında bir tanımı başlatılmalıdır.

Aşağıdaki örnek, C2438 oluşturur:

```
// C2438.cpp
struct X {
   X(int i) : j(i) {}   // C2438
   static int j;
};

int X::j;

int main() {
   X::j = 1;
}
```