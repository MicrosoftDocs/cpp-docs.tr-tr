---
title: /STACK
ms.date: 11/04/2016
f1_keywords:
- /stack
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
ms.openlocfilehash: 6f30877800d4597054601f7459df88c78193fd3c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318504"
---
# <a name="stack"></a>/STACK

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, yığın boyunu bayt cinsinden ayarlar ve ondalık ya da C dili gösteriminde bağımsız değişkeni alır. /STACK seçeneği yalnızca bir yürütülebilir dosya için geçerlidir.

*Rezerve* bağımsız değişkeni sanal bellekte toplam yığın ayırma belirtir. Belirtilen değeri en yakın 4 bayt EDITBIN yuvarlar.

İsteğe bağlı `commit` bağımsız değişkeni, işletim sistemi tarafından yorumu tabidir. Windows NT, Windows 95 ve Windows 98 `commit` teker teker ayrılacak fiziksel bellek miktarını belirtir. Yürütülen sanal bellek disk belleği dosyasında ayrılacak alanı neden olur. Daha yüksek bir `commit` değeri kaydeder süre olduğunda, uygulama daha fazla yığın alanı gerekiyor ancak bellek gereksinimleri ve büyük olasılıkla başlatma süresini artırır.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](editbin-options.md)
