---
description: "Daha fazla bilgi edinin: COM 'a giriş"
title: COM'a Giriş
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
ms.openlocfilehash: 635bce8c1214dddfc258ae6d2d6c7e751f778e9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147673"
---
# <a name="introduction-to-com"></a>COM'a Giriş

COM, ActiveX denetimlerinin ve OLE 'nin oluşturulduğu temel "nesne modelidir". COM, bir nesnenin işlevselliğini diğer bileşenlere sergileme ve uygulamaları barındırmasına olanak tanır. Nesnenin kendisini nasıl kullanıma sunduğunu ve bu pozlamayı süreçler ve ağlar arasında nasıl çalıştığını tanımlar. COM Ayrıca nesnenin yaşam döngüsünü tanımlar.

Temel-COM aşağıdaki kavramlardır:

- [Arabirimler](../atl/interfaces-atl.md) — bir nesnenin işlevlerini kullanıma sunma mekanizması.

- [IUnknown](../atl/iunknown.md) — tüm diğerlerinin temel aldığı temel arabirim. COM üzerinden çalışan başvuru saymasını ve arabirim sorgulama mekanizmalarını uygular.

- [Başvuru sayımı](../atl/reference-counting.md) — bir nesnenin (ya da tamamen, bir arabirimin) artık kullanılmıyor olmasının ne zaman karar verdiği ve bu nedenle kendisini kaldırmak için boş olan teknik.

- [QueryInterface](../atl/queryinterface.md) — belirli bir arabirim için bir nesneyi sorgulamak için kullanılan yöntem.

- [Sıralama](../atl/marshaling.md) — nesnelerin iş parçacığı, süreç ve ağ sınırları genelinde kullanılmasını sağlayan mekanizma, konum bağımsızlığı için izin verir.

- [Toplama](../atl/aggregation.md) — bir nesnenin diğeri tarafından ne şekilde kullanılabilir hale sunılabileceği bir yoldur.

## <a name="see-also"></a>Ayrıca bkz.

[COM ve ATL'ye Giriş](../atl/introduction-to-com-and-atl.md)<br/>
[Bileşen nesne modeli](/windows/win32/com/the-component-object-model)
