---
title: Derleyici Hatası C3769
ms.date: 11/04/2016
f1_keywords:
- C3769
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
ms.openlocfilehash: 68845b446541b8d76ebd2b873a34b7e32ef314e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480359"
---
# <a name="compiler-error-c3769"></a>Derleyici Hatası C3769

'type': iç içe geçmiş bir sınıf kapsayan sınıf ile aynı ada sahip olamaz

İç içe geçmiş bir sınıf kapsayan sınıf ile aynı ada sahip olamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3769 oluşturur.

```
// C3769.cpp
// compile with: /c
class x {
   class x {};   // C3769
   class y {
      class x{};   // OK
   };
};
```