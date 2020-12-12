---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4343'
title: Derleyici Uyarısı (düzey 4) C4343
ms.date: 11/04/2016
f1_keywords:
- C4343
helpviewer_keywords:
- C4343
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
ms.openlocfilehash: 906dee40eb0e9ef55c67657e93f42a6e2279a9d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294502"
---
# <a name="compiler-warning-level-4-c4343"></a>Derleyici Uyarısı (düzey 4) C4343

\#pragma optimize ("g", off) geçersiz kılmaları/OG seçeneği

Bu uyarı, yalnızca Itanium Işlemci ailesi (ıPF) derleyicisi için geçerlidir, bir pragma 'ın overrode bir [/OG](../../build/reference/og-global-optimizations.md) derleyici seçeneğini [iyileştirmesi](../../preprocessor/optimize.md) gerektiğini bildiriyor.

Aşağıdaki örnek C4343 oluşturur:

```cpp
// C4343.cpp
// compile with: /Og /W4 /LD
// processor: IPF
#pragma optimize ("g", off)   // C4343
```
