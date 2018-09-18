---
title: Derleyici Hatası C3285 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3285
dev_langs:
- C++
helpviewer_keywords:
- C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 685d83f224cc0b6c259a2fdf6946f28d909a1e6b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049572"
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