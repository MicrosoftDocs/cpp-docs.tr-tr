---
title: Toplama
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
ms.openlocfilehash: 288af427bd6a8d9baf572dfad8e4a25452694ad9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491979"
---
# <a name="aggregation"></a>Toplama

Bir nesnenin uygulayıcısı, başka, önceden oluşturulmuş bir nesne tarafından sunulan hizmetlerden faydalanmak için zaman alır. Ayrıca, bu ikinci nesnenin birincinin doğal bir parçası olarak görünmesini istiyor. COM, kapsama ve toplama aracılığıyla bu hedeflerin her ikisine de erişir.

Toplama, kapsayan (dış) nesnenin oluşturma işleminin bir parçası olarak içerilen (iç) nesneyi oluşturduğu ve iç nesne arabirimlerinin dıştaki tarafından sunulduğunu gösterir. Bir nesne kendi kendine toplanabilir olmasına izin verir. Bu durumda, toplama işleminin düzgün şekilde çalışması için bazı kuralları izlemesi gerekir.

Birincil olarak, `IUnknown` içerilen nesne üzerindeki tüm Yöntem çağrıları kapsayan nesneye temsilci seçme olmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[Nesneleri yeniden kullanma](/windows/win32/com/reusing-objects)
