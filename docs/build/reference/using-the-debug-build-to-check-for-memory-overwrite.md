---
title: "Belleğin üzerine yazma için onay hata ayıklama derlemesini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7b8fc223a1e4e1162ce99bb3275152c49828aa99
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>Belleğin Üzerine Yazma Denetimi için Hata Ayıklama Derlemesini Kullanma
Belleğin üzerine yazma için denetlemek için hata ayıklama derlemesi kullanmak için ilk projeniz hata ayıklama için yeniden oluşturmanız gerekir. Ardından, uygulamanızın çok başlangıcına Git `InitInstance` işlev ve aşağıdaki satırı ekleyin:  
  
```  
afxMemDF |= checkAlwaysMemDF;  
```  
  
 Hata ayıklama bellek ayırıcısı koruma bayt tüm bellek ayırmaları geçici koyar. Ancak, bunlar bayt koruma (hangi belleğin üzerine yazma gösterir) değiştirildikten olup olmadığını denetleyin sürece tüm iyi desteklemez. Aksi takdirde, bu yalnızca aslında, belleğin üzerine yazma ile hemen almak için izin verebilir bir arabellek sağlar.  
  
 Açarak `checkAlwaysMemDF`, MFC çağırmaya zorlayacağı `AfxCheckMemory` her işlev çağrısı için **yeni** veya **silmek** yapılır. Belleğin üzerine yazma algılandı, aşağıdakine benzer bir izleme iletisi oluşturur:  
  
```  
Damage Occurred! Block=0x5533  
```  
  
 Bu iletiler birini görürseniz, hasarı nerede oluştuğunu belirlemek için kodunuzu adım gerekir. Belleğin üzerine yazma oluştuğu daha kesin olarak ayırmak için açık çağrılar yapabilirsiniz `AfxCheckMemory` kendiniz. Örneğin:  
  
```  
ASSERT(AfxCheckMemory());  
    DoABunchOfStuff();  
    ASSERT(AfxCheckMemory());  
```  
  
 İlk ASSERT başarılı ve ikincisi başarısız olursa, belleğin üzerine yazma işlevi iki çağrılar arasında oluşan gerekir anlamına gelir.  
  
 Uygulamanızı yapısına bağlı açamayabilirsiniz `afxMemDF` programınızı bile test etmek için çok yavaş çalışmasına neden olur. `afxMemDF` Değişkeni neden `AfxCheckMemory` her çağrı için yeni çağrılması ve silmek için. Bu durumda, kendi çağrıları dağılım `AfxCheckMemory`(yukarıda gösterildiği gibi) ve bellek ayırmak için try üzerine bu şekilde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yayın derlemesi sorunlarını giderme](../../build/reference/fixing-release-build-problems.md)