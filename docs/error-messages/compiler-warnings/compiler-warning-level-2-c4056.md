---
title: Derleyici Uyarısı (düzey 2) C4056
ms.date: 11/04/2016
f1_keywords:
- C4056
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
ms.openlocfilehash: 20e7c2693c14c0ea05cc6f07f8dad4ce76c1ef5e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052187"
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