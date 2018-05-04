---
title: -STACK | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /stack
dev_langs:
- C++
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a82111ce950d14bc6b3e270ee9a658d806b28b62
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="stack"></a>/STACK
```  
/STACK:reserve[,commit]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek yığın boyutunu bayt cinsinden ayarlar ve ondalık ya da C dili gösterimde bağımsız değişkenleri alır. /STACK seçeneği yalnızca yürütülebilir bir dosya için geçerlidir.  
  
 *Yedek* bağımsız değişkeni, sanal bellek toplam yığın ayırma belirtir. EDITBIN yakın 4 bayt belirtilen değere yukarı yuvarlar.  
  
 İsteğe bağlı `commit` bağımsız değişkeni, işletim sistemi tarafından tercüme tabidir. Windows NT, Windows 95 ve Windows 98 `commit` aynı anda ayırmak için fiziksel bellek miktarını belirtir. Kaydedilebilen sanal bellek disk belleği dosyasında ayrılacak alanı neden olur. Yüksek bir `commit` değeri kaydeder süre olduğunda, uygulama daha fazla yığın alanı gerekiyor ancak bellek gereksinimlerini ve büyük olasılıkla başlangıç zamanını artırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EDITBIN Seçenekleri](../../build/reference/editbin-options.md)