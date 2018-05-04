---
title: COM giriş | Microsoft Docs
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 938d0c45cae5ec9a2988f77f539af1a3d5513b83
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="introduction-to-com"></a>COM giriş
COM, hangi ActiveX denetimlerinin ve OLE üzerine kuruludur "nesne modeli" temel alanıdır. COM diğer bileşenler ve konak uygulamaların işlevselliğini kullanıma sunmak bir nesne sağlar. Hem nesnenin kendisini nasıl kullanıma sunar ve bu Etkilenme ağlar ve işlemler arasında nasıl çalıştığını tanımlar. COM nesnesinin yaşam döngüsü da tanımlar.  
  
 Bu kavramlar COM temel şunlardır:  
  
-   [Arabirimleri](../atl/interfaces-atl.md) — bir nesne işlevselliği sunan mekanizması.  
  
-   [IUnknown](../atl/iunknown.md) — diğer tüm bağlı temel arabirimi. Başvuru sayım ve COM çalışan mekanizmaları sorgulama arabirimi uygulayan  
  
-   [Başvuru sayım](../atl/reference-counting.md) — tarafından bir nesne (ya da kesinlikle, bir arabirim) yazılacağı zaman artık kullanılıyor ve bu nedenle kendisini kaldırmak ücretsiz teknik.  
  
-   [QueryInterface](../atl/queryinterface.md) — bir nesne belirli bir arabirim için sorgulamak için kullanılan yöntem.  
  
-   [Hazırlama](../atl/marshaling.md) — iş parçacığı, işlem ve konum bağımsızlığı için izin vererek ağ sınırları boyunca kullanılacak nesneler sağlayan mekanizması.  
  
-   [Toplama](../atl/aggregation.md) — bir nesne yapabilir şekilde başka kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM ve ATL giriş](../atl/introduction-to-com-and-atl.md)   
 [Bileşen Nesne modeli](http://msdn.microsoft.com/library/windows/desktop/ms694363)

