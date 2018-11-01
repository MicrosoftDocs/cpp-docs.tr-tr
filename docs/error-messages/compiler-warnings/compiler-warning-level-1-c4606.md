---
title: Derleyici Uyarısı (düzey 1) C4606
ms.date: 11/04/2016
f1_keywords:
- C4606
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
ms.openlocfilehash: e471ca3e478d1166b150e49bf25efa4b9d5803cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569279"
---
# <a name="compiler-warning-level-1-c4606"></a>Derleyici Uyarısı (düzey 1) C4606

\#pragma uyarısı: 'warning_number yoksayıldı;' Kod çözümleme uyarıları, uyarı düzeyleriyle ilişkili değil.

Kod Analizi uyarıları, yalnızca için `error`, `once`, ve `default` ile desteklenen [uyarı](../../preprocessor/warning.md) pragması.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4606 oluşturur.

```
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```