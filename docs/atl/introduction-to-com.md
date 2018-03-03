---
title: "COM giriş | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a8953949e722265afabc22410174b84c017276c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

