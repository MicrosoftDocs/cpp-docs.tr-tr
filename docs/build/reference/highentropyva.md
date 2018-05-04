---
title: -HIGHENTROPYVA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /HIGHENTROPYVA
dev_langs:
- C++
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 122f524db9af10449ce809e5a8de78148d04d431
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="highentropyva"></a>/HIGHENTROPYVA
Yürütülebilir görüntü yüksek entropi 64-bit adres boşluğu düzeni rastgele seçimini (ASLR) destekleyip desteklemediğini belirtir.  
  
```  
  
/HIGHENTROPYVA[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek bir .dll veya .exe dosyasının ASLR 64-bit adresleriyle desteklenip desteklenmediğini belirtmek için üstbilgisinin değiştirir. Bu seçenek, yürütülebilir bir dosya ve tüm bağımlı modülleri ayarlandığında, 64 bit ASLR destekleyen bir işletim sistemi yürütülebilir görüntü parçalarını yükleme zamanında bir 64-bit sanal adres alanı rastgele adreslerini kullanarak rebase. Bu büyük adres alanı bir saldırganın belirli bellek bölge konumunu tahmin edilmesi daha zor hale getirir.  
  
 Varsayılan olarak, bağlayıcı 64-bit yürütülebilir görüntüler için bu seçeneği ayarlar. Bu seçeneği belirlemek için [/DYNAMICBASE](../../build/reference/dynamicbase.md) seçeneği de ayarlanması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EDITBIN seçenekleri](../../build/reference/editbin-options.md)   
 [/ DYNAMICBASE](../../build/reference/dynamicbase.md)   
 [Windows ISV yazılım güvenlik Savunmaları](http://msdn.microsoft.com/library/bb430720.aspx)