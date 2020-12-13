---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3285'
title: Derleyici hatası C3285
ms.date: 11/04/2016
f1_keywords:
- C3285
helpviewer_keywords:
- C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
ms.openlocfilehash: d5b57b878ed47118e1857558b9d633bb5ef7286c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339338"
---
# <a name="compiler-error-c3285"></a>Derleyici hatası C3285

for each deyimleri, ' Type ' türündeki değişkenlerde çalışamaz

`for each`Deyimi bir dizideki veya nesne koleksiyonundaki her öğe için gömülü deyimler grubunu yineler.

Daha fazla bilgi için [,](../../dotnet/for-each-in.md) bkz..

## <a name="example"></a>Örnek

Aşağıdaki örnek C3285 oluşturur.

```cpp
// C3285.cpp
// compile with: /clr
int main() {
   for each (int i in 0) {}   // C3285

   array<int> ^p = { 1, 2, 3 };
   for each (int j in p) {}   // OK
}
```
