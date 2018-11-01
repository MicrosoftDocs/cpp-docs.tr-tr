---
title: Derleyici Hatası C3285
ms.date: 11/04/2016
f1_keywords:
- C3285
helpviewer_keywords:
- C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
ms.openlocfilehash: 6bc211fb2394a9a2989702c13e19bd63ea8a5ad7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444635"
---
# <a name="compiler-error-c3285"></a>Derleyici Hatası C3285

for each deyimi 'type' türündeki değişkenlerde çalışamaz

`for each` Deyimi bir dizideki veya nesne koleksiyonundaki her öğe için bir katıştırılmış deyim grubunu yineler.

Bkz: [her, içinde](../../dotnet/for-each-in.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3285 oluşturur.

```
// C3285.cpp
// compile with: /clr
int main() {
   for each (int i in 0) {}   // C3285

   array<int> ^p = { 1, 2, 3 };
   for each (int j in p) {}   // OK
}
```