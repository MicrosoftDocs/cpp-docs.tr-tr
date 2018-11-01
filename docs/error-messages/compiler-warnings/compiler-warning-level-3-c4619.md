---
title: Derleyici Uyarısı (Düzey 3) C4619
ms.date: 11/04/2016
f1_keywords:
- C4619
helpviewer_keywords:
- C4619
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
ms.openlocfilehash: 00647e7dafe18ffad2a059b960ebed0a0f4a5d36
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580273"
---
# <a name="compiler-warning-level-3-c4619"></a>Derleyici Uyarısı (Düzey 3) C4619

\#pragma uyarısı: uyarı numarası 'number' yok

Var olmayan bir uyarıyı devre dışı bırakmak için girişimde bulunuldu.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

Aşağıdaki örnek, C4619 oluşturur:

```
// C4619.cpp
// compile with: /W3 /c
#pragma warning(default : 4619)
#pragma warning(disable : 4354)   // C4619, C4354 does not exist
```