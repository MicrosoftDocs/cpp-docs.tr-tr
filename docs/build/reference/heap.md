---
title: -YIĞIN | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /heap
dev_langs:
- C++
helpviewer_keywords:
- heap allocation, setting heap size
- HEAP editbin option
- -HEAP editbin option
- /HEAP editbin option
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22698760ba23dc60b64002f0f728bb7a036f6731
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699822"
---
# <a name="heap"></a>/HEAP

Yığın boyutunu bayt cinsinden ayarlar. Bu seçenek, yalnızca yürütülebilir dosyalar için geçerlidir.

```

/HEAP:
reserve[,commit]
```

## <a name="remarks"></a>Açıklamalar

`reserve` Bağımsız değişkeni, ilk toplam yığın ayırma sanal bellekte belirtir. Varsayılan olarak, 1 MB öbek boyutudur. [EDITBIN başvurusu](../../build/reference/editbin-reference.md) belirtilen değer en yakın katına 4 baytlık yukarı yuvarlar.

İsteğe bağlı `commit` bağımsız değişkeni, işletim sistemi tarafından yorumu tabidir. Bir Windows işletim sisteminde ilk ayrılacak fiziksel bellek miktarı ve yığın genişletilmiş olduğunda ayırmak için ek bellek miktarını belirtir. Yürütülen sanal bellek disk belleği dosyasında ayrılacak alanı neden olur. Daha yüksek bir `commit` değer, uygulama genellikle daha fazla yığın alanı gerekiyor ancak bellek gereksinimleri ve büyük olasılıkla uygulama başlatma süresini artırır, daha az bellek ayırmak sistemi sağlar. `commit` Değeri küçük veya buna eşit olmalıdır `reserve` değeri.

Belirtin `reserve` ve `commit` değerleri ondalık ya da C dili onaltılık veya sekizlik gösterim. Örneğin, 1 MB değeri, ondalık, 1048576 olarak veya 0x100000 onaltılık veya sekizlik olarak 04000000 olarak belirtilebilir.

## <a name="see-also"></a>Ayrıca Bkz.

[EDITBIN Seçenekleri](../../build/reference/editbin-options.md)