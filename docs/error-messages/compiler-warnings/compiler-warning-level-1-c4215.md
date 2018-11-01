---
title: Derleyici Uyarısı (düzey 1) C4215
ms.date: 11/04/2016
f1_keywords:
- C4215
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
ms.openlocfilehash: a45cd6cf86eb8ab1edb33ad5e0df8374972c425e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450831"
---
# <a name="compiler-warning-level-1-c4215"></a>Derleyici Uyarısı (düzey 1) C4215

Standart olmayan uzantı kullanıldı: kayan uzun

Varsayılan Microsoft Uzatmaları (/Ze) kabul **uzun kayan nokta** olarak **çift**. ANSI uyumluluğu ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) desteklemez. Kullanım **çift** uyumluluğu korumak için.

Aşağıdaki örnek, C4215 oluşturur:

```
// C4215.cpp
// compile with: /W1 /LD
long float a;   // C4215

// use the line below to resolve the warning
// double a;
```