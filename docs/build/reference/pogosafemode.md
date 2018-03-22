---
title: PogoSafeMode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- PogoSafeMode
ms.assetid: 2daeeff7-44cb-417f-90eb-6b9edf658533
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5f40dad6feff9e49deeb495e8acbf2584dea3e41
ms.sourcegitcommit: 5cd2e3e51ecc8d9fc0d889555b4bfa193ba1d6a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2018
---
# <a name="pogosafemode"></a>PogoSafeMode
Hızlı mod veya güvenli mod uygulama profili oluşturma için kullanılıp kullanılmayacağını belirtin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
PogoSafeMode  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Profil temelli iyileştirme (PGO) sahip iki olası modları profil oluşturma aşamasında: hızlı mod ve güvenli modda. Profil oluşturma Hızlı modunda olduğunda kullanan **Inc** veri sayaçları artırmak için yönerge. **Inc** yönerge hızlıdır ancak iş parçacığı açısından güvenli değil. Profil oluşturma güvenli modda olduğunda, kullanan **kilit Inc** veri sayaçları artırmak için yönerge. **Kilit Inc** yönerge olan ile aynı işlevselliği **Inc** yönergesi sahiptir ve iş parçacığı güvenlidir, ancak daha yavaştır **Inc** yönergesi.  
  
 Varsayılan olarak, PGO profil hızlı modunda çalışır. `PogoSafeMode` olduğundan yalnızca güvenli mod kullanmak istiyorsanız gereklidir.  
  
 Güvenli modda PGO profil çalıştırmak için ya da ortam değişkeni kullanmanız gerekir `PogoSafeMode` ya da bağlayıcı anahtar **- PogoSafeMode**sistemine bağlı olarak. Profil oluşturma x x64 üzerinde gerçekleştirdiğiniz, bilgisayar, bağlayıcı anahtarı kullanmanız gerekir. Profil oluşturma x x86 üzerinde gerçekleştirdiğiniz varsa bilgisayar tanımlamalısınız ortam değişkeni için herhangi bir değer, en iyi duruma getirme işlemine başlamadan önce.  
  
## <a name="example"></a>Örnek  
  
```  
set PogoSafeMode=1  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Profil temelli iyileştirmeler için ortam değişkenleri](../../build/reference/environment-variables-for-profile-guided-optimizations.md)   
 [Profil Temelli İyileştirmeler](../../build/reference/profile-guided-optimizations.md)