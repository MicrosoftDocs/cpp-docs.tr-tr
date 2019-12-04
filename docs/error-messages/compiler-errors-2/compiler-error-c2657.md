---
title: Derleyici hatası C2657
ms.date: 11/04/2016
f1_keywords:
- C2657
helpviewer_keywords:
- C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
ms.openlocfilehash: e060c2b9a38866a898a3c5ada9e595464050877e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756103"
---
# <a name="compiler-error-c2657"></a>Derleyici hatası C2657

deyimin başlangıcında ' class::* ' bulundu (bir tür belirtmeyi unuttunuz mu?)

Satır, üye işaretçisi tanımlayıcısı ile başladı.

Bu hata, bir üyenin işaretçisinin bildiriminde eksik tür belirticisinden kaynaklanabilir.

Aşağıdaki örnek C2657 oluşturur:

```cpp
// C2657.cpp
class C {};
int main() {
   C::* pmc1;        // C2657
   int C::* pmc2;   // OK
}
```
