---
title: Derleyici Hatası C2021
ms.date: 11/04/2016
f1_keywords:
- C2021
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
ms.openlocfilehash: 6492dfffbb5a2f80ea543d4248c0f77759c0a521
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514016"
---
# <a name="compiler-error-c2021"></a>Derleyici Hatası C2021

'character' değil üs değeri bekleniyordu

Bir kayan noktalı sabit ' üs kullanılan karakter, geçerli bir sayı değil. Aralıktaki bir üs kullandığınızdan emin olun.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2021 oluşturur:

```
// C2021.cpp
float test1=1.175494351E;   // C2021
```

## <a name="example"></a>Örnek

Olası çözüm:

```
// C2021b.cpp
// compile with: /c
float test2=1.175494351E8;
```