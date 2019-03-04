---
title: Toplama
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
ms.openlocfilehash: 2eec7a801f9fe16bc48fc888d10ce413ec7e79db
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265437"
---
# <a name="aggregation"></a>Toplama

Bir nesnenin uygulamacının başka bir, önceden oluşturulmuş bir nesne tarafından sunulan hizmetler yararlanmak için ne zaman istediğiniz zamanlar vardır. Ayrıca, bu ikinci nesne ilk doğal bir parçası olarak görünmesini istediğiniz. COM, her ikisi de elde eder, bu hedefleri kapsama ve toplama.

Toplama içeren (Dış) nesnenin içerdiği (iç), oluşturma işleminin bir parçası olarak oluşturur ve arabirimler iç nesne dış tarafından sunulan anlamına gelir. Bir nesne kendisine veya bir araya toplanabilir olmasını sağlar. İse, düzgün çalışması Toplama için belirli kuralları izlemelidir.

Öncelikle, tüm `IUnknown` kapsanan nesne üzerinde yöntem çağrılarını içeren nesneye temsilci gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[Nesneleri yeniden kullanma](/windows/desktop/com/reusing-objects)
