---
title: -STACK | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /stack
dev_langs: C++
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 21438bf8f214c10525aa7e9a5829f835b8a33f2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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