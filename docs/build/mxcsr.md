---
title: MxCsr
ms.date: 11/04/2016
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
ms.openlocfilehash: d411223634aec6d11413ac1f5b1fb04dba7498e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497382"
---
# <a name="mxcsr"></a>MxCsr

Kayıt durumu MxCsr de içerir. Çağırma kuralı bu kayıt, geçici ve kalıcı bir bölümü böler. MXCSR 6 durumu bayrakları geçici bir bölümü oluşur [0:5], kayıt, [6:15] MXCSR geri kalanında kalıcı olarak değerlendirilir.

Kalıcı bölümü, program yürütme başlangıcında standart aşağıdaki değerlere ayarlanır:

```
MXCSR[6]         : Denormals are zeros - 0
MXCSR[7:12]      : Exception masks all 1's (all exceptions masked)
MXCSR[13:14]   : Rounding  control - 0 (round to nearest)
MXCSR[15]      : Flush to zero for masked underflow - 0 (off)
```

Kalıcı alanlar MXCSR içinde değiştiren bir çağrılan çağırana döndürülmeden önce bunları geri yüklemelisiniz. Ayrıca, bu alanların değiştirdiği bir çağıranın bunları standart değerlerine sözleşmesiyle çağrılan değiştirilen değerlerin bekliyor sürece çağrılan çağırmadan önce geri yüklemeniz gerekir.

Denetim bayrakları, olmayan-volatility ilgili kuralları iki istisna mevcuttur:

- Kalıcı MxCsr değiştirmek için verilen işlevi belgelenen amacı olduğu işlevlerde işaretler.

- Bu kural ihlalini davranışını/bir program burada bu kurallar, örneğin, tüm program Analizi ile ihlal edilmemesi ile aynı anlamına gelir, bir program sonuçları kanıtlanabilir geldiğinde düzeltin.

Hiçbir varsayım özellikle bir işlevin belgelerinde açıklanan sürece MXCSR geçici kısmı bir işlev sınırı arasında durumuyla ilgili yapılabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Çağırma Kuralı](../build/calling-convention.md)