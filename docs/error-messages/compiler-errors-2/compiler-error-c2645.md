---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2645'
title: Derleyici hatası C2645
ms.date: 11/04/2016
f1_keywords:
- C2645
helpviewer_keywords:
- C2645
ms.assetid: 6609c2fa-c3b2-4a6b-8e8d-58fb52f67175
ms.openlocfilehash: d757b171fd314a5ed90fafe76d1b45074ec5b604
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160837"
---
# <a name="compiler-error-c2645"></a>Derleyici hatası C2645

üyeye işaretçisinin nitelenmiş adı yok (':: * ' bulundu)

Bir üyeye yönelik işaretçinin bildirimi bir sınıf belirtmiyor.

Aşağıdaki örnek C2645 oluşturur:

```cpp
// C2645.cpp
class A {};
int main() {
   int B::* bp;   // C2645 B not defined
   int A::* ap;   // OK
}
```
