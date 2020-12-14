---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2438'
title: Derleyici hatası C2438
ms.date: 11/04/2016
f1_keywords:
- C2438
helpviewer_keywords:
- C2438
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
ms.openlocfilehash: 1400ee013e5d507f7fdfe288b97db10ec8216085
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189892"
---
# <a name="compiler-error-c2438"></a>Derleyici hatası C2438

' tanımlayıcı ': statik sınıf verileri Oluşturucu aracılığıyla başlatılamaz

Bir Oluşturucu, bir sınıfın statik bir üyesini başlatmak için kullanılır. Statik üyelerin, sınıf bildiriminin dışında bir tanımda başlatılması gerekir.

Aşağıdaki örnek C2438 oluşturur:

```cpp
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
