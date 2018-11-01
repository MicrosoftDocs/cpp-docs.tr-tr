---
title: Prototipi Oluşturulmamış İşlevler
ms.date: 11/04/2016
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
ms.openlocfilehash: 38207be6111dadc338593e55b683b88e0480e1ca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633435"
---
# <a name="unprototyped-functions"></a>Prototipi Oluşturulmamış İşlevler

Değil tam prototipi oluşturulmuş işlevler için çağırana tamsayı değerleri tamsayı ve kayan nokta değerleri çift duyarlık olarak geçer. Aranan değer tamsayı kayıtlara bekliyor durumunda yalnızca kayan nokta değerleri için float değeri hem tamsayı kaydı ve kayan nokta kaydı içerir.

```
func1();
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7
   func1(2, 1.0, 7);
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Çağırma Kuralı](../build/calling-convention.md)