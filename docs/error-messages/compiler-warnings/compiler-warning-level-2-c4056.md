---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 2) C4056'
title: Derleyici Uyarısı (düzey 2) C4056
ms.date: 11/04/2016
f1_keywords:
- C4056
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
ms.openlocfilehash: 5d8b96e97197e43bf288476e310ddd842a90ec48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326550"
---
# <a name="compiler-warning-level-2-c4056"></a>Derleyici Uyarısı (düzey 2) C4056

kayan noktalı sabit aritmetik işleminde taşma

Kayan noktalı sabit aritmetik, izin verilen en yüksek değeri aşan bir sonuç oluşturuyor.

Bu uyarı, sabit aritmetik sırasında gerçekleştirilen derleyici iyileştirmelerinden kaynaklanabilir. İyileştirme 'yi ([/od](../../build/reference/od-disable-debug.md)) kapattığınızda bu uyarıyı güvenle yoksayabilirsiniz.

Aşağıdaki örnek C4056 oluşturur:

```cpp
// C4056.cpp
// compile with: /W2 /LD
#pragma warning (default : 4056)
float fp_val = 1.0e300 * 1.0e300;   // C4056
```
