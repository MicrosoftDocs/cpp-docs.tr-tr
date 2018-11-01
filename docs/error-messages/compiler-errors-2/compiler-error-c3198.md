---
title: Derleyici Hatası C3198
ms.date: 11/04/2016
f1_keywords:
- C3198
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
ms.openlocfilehash: 61a3d14f9ad47edaa1e9b9f2b25d38b8dae7165c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567459"
---
# <a name="compiler-error-c3198"></a>Derleyici Hatası C3198

kayan noktalı pragmaların geçersiz kullanımı: fenv_access pragma yalnızca hassas modda çalışır

[fenv_access](../../preprocessor/fenv-access.md) pragma altında kullanıldı bir [/FP](../../build/reference/fp-specify-floating-point-behavior.md) dışında ayarlama **/FP: precise**.

Aşağıdaki örnek, C3198 oluşturur:

```
// C3198.cpp
// compile with: /fp:fast
#pragma fenv_access(on)   // C3198
```