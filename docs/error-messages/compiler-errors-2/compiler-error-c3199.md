---
title: Derleyici Hatası C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 934e980149ad893e6799b0ab119a148fc5652fdc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402794"
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