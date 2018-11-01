---
title: Derleyici Hatası C2449
ms.date: 11/04/2016
f1_keywords:
- C2449
helpviewer_keywords:
- C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
ms.openlocfilehash: f674bbec7cee8c00792848ee7e51b1e46299dd58
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655344"
---
# <a name="compiler-error-c2449"></a>Derleyici Hatası C2449

bulunan ' {' dosya kapsamında (işlev üstbilgisi eksik?)

Açık bir ayraç dosya kapsamında gerçekleşir.

Bu hata, bir işlev üstbilgisi işlev tanımının açılış ayracından arasındaki noktalı neden olabilir.

Aşağıdaki örnek, C2499 oluşturur:

```
// C2449.c
// compile with: /c
void __stdcall func(void) {}   // OK
void __stdcall func(void);  // extra semicolon on this line
{                         // C2449 detected here
```