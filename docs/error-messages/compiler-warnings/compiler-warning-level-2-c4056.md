---
title: Derleyici Uyarısı (düzey 2) C4056
ms.date: 11/04/2016
f1_keywords:
- C4056
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
ms.openlocfilehash: 6046c41bfe9d787732a2cbd50ce3b0d0d9fdb26f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174355"
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
