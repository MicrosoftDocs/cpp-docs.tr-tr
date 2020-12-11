---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3199'
title: Derleyici hatası C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 598d21edbddc91d39edb9623dc59537d3e27bdf3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155481"
---
# <a name="compiler-error-c3199"></a>Derleyici hatası C3199

kayan noktalı pragmaların geçersiz kullanımı: özel durumlar, kesin olmayan modda desteklenmez

[Float_control](../../preprocessor/float-control.md) pragma, **/FP: kesinlikli** bir [/FP](../../build/reference/fp-specify-floating-point-behavior.md) ayarı altında kayan nokta özel durum modelini belirtmek için kullanıldı.

Aşağıdaki örnek C3199 oluşturur:

```cpp
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```
