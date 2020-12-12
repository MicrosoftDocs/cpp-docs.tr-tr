---
description: 'Daha fazla bilgi edinin: toplama'
title: Toplama
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
ms.openlocfilehash: fb02dd399020f8768fcdb3cc86687578e51cb3ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166102"
---
# <a name="aggregation"></a>Toplama

Bir nesnenin uygulayıcısı, başka, önceden oluşturulmuş bir nesne tarafından sunulan hizmetlerden faydalanmak için zaman alır. Ayrıca, bu ikinci nesnenin birincinin doğal bir parçası olarak görünmesini istiyor. COM, kapsama ve toplama aracılığıyla bu hedeflerin her ikisine de erişir.

Toplama, kapsayan (dış) nesnenin oluşturma işleminin bir parçası olarak içerilen (iç) nesneyi oluşturduğu ve iç nesne arabirimlerinin dıştaki tarafından sunulduğunu gösterir. Bir nesne kendi kendine toplanabilir olmasına izin verir. Bu durumda, toplama işleminin düzgün şekilde çalışması için bazı kuralları izlemesi gerekir.

Birincil olarak, `IUnknown` içerilen nesne üzerindeki tüm Yöntem çağrıları kapsayan nesneye temsilci seçme olmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[COM'a Giriş](../atl/introduction-to-com.md)<br/>
[Nesneleri yeniden kullanma](/windows/win32/com/reusing-objects)
