---
title: Toplama
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
ms.openlocfilehash: d5a09dcd8c289447491ebc7111a77549166a7d00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633424"
---
# <a name="aggregation"></a>Toplama

Bir nesnenin uygulamacının başka bir, önceden oluşturulmuş bir nesne tarafından sunulan hizmetler yararlanmak için ne zaman istediğiniz zamanlar vardır. Ayrıca, bu ikinci nesne ilk doğal bir parçası olarak görünmesini istediğiniz. COM, her ikisi de elde eder, bu hedefleri kapsama ve toplama.

Toplama içeren (Dış) nesnenin içerdiği (iç), oluşturma işleminin bir parçası olarak oluşturur ve arabirimler iç nesne dış tarafından sunulan anlamına gelir. Bir nesne kendisine veya bir araya toplanabilir olmasını sağlar. İse, düzgün çalışması Toplama için belirli kuralları izlemelidir.

Öncelikle, tüm `IUnknown` kapsanan nesne üzerinde yöntem çağrılarını içeren nesneye temsilci gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[Nesneleri yeniden kullanma](/windows/desktop/com/reusing-objects)

