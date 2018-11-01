---
title: COM'a giriş
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
ms.openlocfilehash: 7a200a964e0cba09878929e4362385e5badd10c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492881"
---
# <a name="introduction-to-com"></a>COM'a giriş

COM, hangi ActiveX denetimlerinin ve OLE oluşturulan temel "nesne modeli" olur. COM diğer bileşenleri ve uygulamaları barındırmak için işlevselliği göstermek bir nesne sağlar. Bu, hem nesnenin kendisini nasıl kullanıma sunar ve bu Etkilenme ağları ve işlemler arasında nasıl çalıştığını tanımlar. Ayrıca, COM nesnenin yaşam döngüsü tanımlar.

Bu kavramlar COM temel şunlardır:

- [Arabirimleri](../atl/interfaces-atl.md) — bir nesne işlevselliği sunan mekanizması.

- [IUnknown](../atl/iunknown.md) — diğer tüm dayalı temel bir arabirim. Başvuru sayımı ve COM içinden çalıştıran mekanizmaları sorgulama arabirimi uygulayan

- [Başvuru sayımı](../atl/reference-counting.md) — teknik olarak bir nesne (ya da kesinlikle, bir arabirim) karar zaman artık kullanılmadığını ve bu nedenle kendisini kaldırmak ücretsiz olarak kullanılabilir.

- [QueryInterface](../atl/queryinterface.md) — belirli bir arabirim için bir nesneyi sorgulamak için kullanılan yöntem.

- [Hazırlama](../atl/marshaling.md) — nesneler iş parçacığı, işlem ve ağ sınırlarını mekandan için izin verme, kullanılacak sağlayan mekanizma.

- [Toplama](../atl/aggregation.md) — bir nesne yapabilir bir şekilde başka birine kullanın.

## <a name="see-also"></a>Ayrıca Bkz.

[COM ve ATL’ye Giriş](../atl/introduction-to-com-and-atl.md)<br/>
[Bileşen Nesne modeli](/windows/desktop/com/the-component-object-model)

