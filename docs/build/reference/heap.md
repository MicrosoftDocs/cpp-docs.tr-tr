---
title: "-YIĞIN | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /heap
dev_langs: C++
helpviewer_keywords:
- heap allocation, setting heap size
- HEAP editbin option
- -HEAP editbin option
- /HEAP editbin option
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 709b9a1b57750db4ea8eb13bdaa3d49eed9b7629
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="heap"></a>/HEAP
Öbek boyutunu bayt cinsinden ayarlar. Bu seçenek yalnızca yürütülebilir dosyaları için geçerlidir.  
  
```  
  
/HEAP:  
reserve[,commit]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `reserve` Bağımsız değişkeni, sanal bellek toplam ilk öbek ayırma belirtir. Varsayılan olarak, yığın boyutu 1 MB'tır. [EDITBIN başvurusu](../../build/reference/editbin-reference.md) belirtilen değeri 4 bayt yakın çarpıma yuvarlar.  
  
 İsteğe bağlı `commit` bağımsız değişkeni, işletim sistemi tarafından tercüme tabidir. Bir Windows işletim sisteminde ilk ayırmak için fiziksel bellek miktarı ve Öbek genişletilmiş olduğunda ayırmak için ek bellek miktarını belirtir. Kaydedilebilen sanal bellek disk belleği dosyasında ayrılacak alanı neden olur. Yüksek bir `commit` değeri genellikle uygulamanın daha fazla yığın alanı gerekiyor ancak bellek gereksinimlerini ve büyük olasılıkla uygulama başlatma süresini artırır, daha az bellek sisteme verir. `commit` Değeri küçük veya eşit olmalıdır `reserve` değeri.  
  
 Belirtin `reserve` ve `commit` değerleri ondalık ya da C dili onaltılık veya sekizlik gösterimi. Örneğin, 1 MB değerini ondalık, 1048576 olarak veya 0x100000 onaltılık veya sekizlik içinde 04000000 olarak belirtilebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EDITBIN seçenekleri](../../build/reference/editbin-options.md)