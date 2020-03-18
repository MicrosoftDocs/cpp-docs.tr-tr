---
title: /STACK
ms.date: 11/04/2016
f1_keywords:
- /stack_editbin
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
ms.openlocfilehash: 63fcddec8ff8afd81084bb5a2786f394db594b07
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438889"
---
# <a name="stack"></a>/STACK

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, yığının boyutunu bayt cinsinden ayarlar ve ondalık ya da C dili gösteriminde bağımsız değişken alır. /STACK seçeneği yalnızca yürütülebilir bir dosya için geçerlidir.

*Reserve* bağımsız değişkeni, sanal bellekteki toplam yığın ayırmayı belirtir. EDITBIN belirtilen değeri en yakın 4 bayta yuvarlar.

İsteğe bağlı `commit` bağımsız değişkeni, işletim sistemi tarafından yorumlamayı tabidir. Windows NT, Windows 95 ve Windows 98 ' de `commit` her seferinde ayrılacak fiziksel bellek miktarını belirtir. Yürütülen sanal bellek, disk belleği dosyasında ayrılan alanın ayrılmasına neden olur. Daha yüksek bir `commit` değeri, uygulamanın daha fazla yığın alanına ihtiyacı olduğunda, ancak bellek gereksinimlerini ve muhtemelen başlangıç süresini arttığında zaman kazandırır.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](editbin-options.md)
