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
ms.openlocfilehash: 5306df647801d7d1467aa0f44bfacca18fccaff3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372223"
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
 [EDITBIN Seçenekleri](../../build/reference/editbin-options.md)