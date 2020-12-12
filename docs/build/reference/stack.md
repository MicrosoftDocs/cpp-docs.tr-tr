---
description: Daha fazla bilgi edinin:/STACK
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
ms.openlocfilehash: 253aec1d760a85f1ebe5dbf7596353b46744cd57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224458"
---
# <a name="stack"></a>/STACK

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, yığının boyutunu bayt cinsinden ayarlar ve ondalık ya da C dili gösteriminde bağımsız değişken alır. /STACK seçeneği yalnızca yürütülebilir bir dosya için geçerlidir.

*Reserve* bağımsız değişkeni, sanal bellekteki toplam yığın ayırmayı belirtir. EDITBIN belirtilen değeri en yakın 4 bayta yuvarlar.

İsteğe bağlı `commit` bağımsız değişken, işletim sistemi tarafından yorumlamayı tabidir. Windows NT, Windows 95 ve Windows 98 ' de, `commit` bir seferde ayrılacak fiziksel bellek miktarını belirtir. Yürütülen sanal bellek, disk belleği dosyasında ayrılan alanın ayrılmasına neden olur. `commit`Uygulamanın daha fazla yığın alanına ihtiyacı olduğunda daha yüksek bir değer zaman kazandırır, ancak bellek gereksinimlerini ve muhtemelen başlangıç süresini arttırır.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN seçenekleri](editbin-options.md)
