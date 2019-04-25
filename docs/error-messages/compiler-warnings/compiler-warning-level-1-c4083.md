---
title: Derleyici Uyarısı (düzey 1) C4083
ms.date: 11/04/2016
f1_keywords:
- C4083
helpviewer_keywords:
- C4083
ms.assetid: e7d3344e-5645-4d56-8460-d1acc9145ada
ms.openlocfilehash: 854d4a9887b8a9ada12adc94509745458a1e9523
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300277"
---
# <a name="compiler-warning-level-1-c4083"></a>Derleyici Uyarısı (düzey 1) C4083

Beklenen 'belirteci'; 'identifier' tanımlayıcısı bulundu

Bir tanımlayıcı yanlış bir yerde oluşan bir **#pragma** deyimi.

## <a name="example"></a>Örnek

```
// C4083.cpp
// compile with: /W1 /LD
#pragma warning disable:4083    // C4083
#pragma warning(disable:4083)   //correct
```

Sözdizimini denetleyin [#pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) yönergeleri.