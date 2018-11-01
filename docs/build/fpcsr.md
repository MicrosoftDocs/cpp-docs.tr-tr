---
title: FpCsr
ms.date: 11/04/2016
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
ms.openlocfilehash: 018ce39a194d5153f73fa452990844362190e6bd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472831"
---
# <a name="fpcsr"></a>FpCsr

Kayıt durumu x87 yöntemlerine FPU denetim sözcüğü. Çağırma kuralı, bu kayıt kalıcı olmasını belirler.

Program yürütmesini x87 FPU denetim sözcük kaydı başlangıcında standart aşağıdaki değerlere ayarlanır:

```
FPCSR[0:6]: Exception masks all 1's (all exceptions masked)
FPCSR[7]: Reserved - 0
FPCSR[8:9]: Precision Control - 10B (double precision)
FPCSR[10:11]: Rounding  control - 0 (round to nearest)
FPCSR[12]: Infinity control - 0 (not used)
```

Herhangi bir alanı olamayan FPCSR içinde değiştiren bir çağrılan çağırana döndürülmeden önce bunları geri yüklemelisiniz. Ayrıca, bu alanların değiştirdiği bir çağıranın bunları standart değerlerine sözleşmesiyle çağrılan değiştirilen değerlerin bekliyor sürece çağrılan çağırmadan önce geri yüklemeniz gerekir.

Denetim bayrakları, olmayan-volatility ilgili kuralları iki istisna mevcuttur:

1. Verilen işlevin amacı belgelenmiş geçici olamayan FpCsr değiştirmek için olduğu işlevlerde işaretler.

1. Bu kural ihlalini davranışını/bir program burada bu kurallar, örneğin, tüm program Analizi ile ihlal edilmemesi ile aynı anlamına gelir, bir program sonuçları kanıtlanabilir geldiğinde düzeltin.

## <a name="see-also"></a>Ayrıca Bkz.

[Çağırma Kuralı](../build/calling-convention.md)