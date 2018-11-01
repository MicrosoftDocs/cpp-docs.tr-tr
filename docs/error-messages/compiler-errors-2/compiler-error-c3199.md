---
title: Derleyici Hatası C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 934e980149ad893e6799b0ab119a148fc5652fdc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578966"
---
# <a name="compiler-error-c3199"></a>Derleyici Hatası C3199

kayan noktalı pragmaların geçersiz kullanımı: özel durumlar hassas olmayan modda desteklenmez

[Float_control](../../preprocessor/float-control.md) pragması, kayan nokta özel durum modeli altında belirtmek için kullanılan bir [/FP](../../build/reference/fp-specify-floating-point-behavior.md) dışında ayarlama **/FP: precise**.

Aşağıdaki örnek, C3199 oluşturur:

```
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```