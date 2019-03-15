---
title: /HEAP
ms.date: 11/04/2016
f1_keywords:
- /heap
helpviewer_keywords:
- heap allocation, setting heap size
- HEAP editbin option
- -HEAP editbin option
- /HEAP editbin option
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
ms.openlocfilehash: fcf557b467ba5bd04352ba2f2702659a1eb2948d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810360"
---
# <a name="heap"></a>/HEAP

Yığın boyutunu bayt cinsinden ayarlar. Bu seçenek, yalnızca yürütülebilir dosyalar için geçerlidir.

```

/HEAP:
reserve[,commit]
```

## <a name="remarks"></a>Açıklamalar

`reserve` Bağımsız değişkeni, ilk toplam yığın ayırma sanal bellekte belirtir. Varsayılan olarak, 1 MB öbek boyutudur. [EDITBIN başvurusu](editbin-reference.md) belirtilen değer en yakın katına 4 baytlık yukarı yuvarlar.

İsteğe bağlı `commit` bağımsız değişkeni, işletim sistemi tarafından yorumu tabidir. Bir Windows işletim sisteminde ilk ayrılacak fiziksel bellek miktarı ve yığın genişletilmiş olduğunda ayırmak için ek bellek miktarını belirtir. Yürütülen sanal bellek disk belleği dosyasında ayrılacak alanı neden olur. Daha yüksek bir `commit` değer, uygulama genellikle daha fazla yığın alanı gerekiyor ancak bellek gereksinimleri ve büyük olasılıkla uygulama başlatma süresini artırır, daha az bellek ayırmak sistemi sağlar. `commit` Değeri küçük veya buna eşit olmalıdır `reserve` değeri.

Belirtin `reserve` ve `commit` değerleri ondalık ya da C dili onaltılık veya sekizlik gösterim. Örneğin, 1 MB değeri, ondalık, 1048576 olarak veya 0x100000 onaltılık veya sekizlik olarak 04000000 olarak belirtilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](editbin-options.md)
