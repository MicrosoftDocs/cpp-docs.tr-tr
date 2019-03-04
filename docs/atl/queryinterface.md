---
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- QueryInterface
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: a3ec3c6e0d2b534c3af49000202461a43a65dae9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261472"
---
# <a name="queryinterface"></a>QueryInterface

Bir nesne express statik olarak (Bu örneği oluşturulmadan) sağladığı işlevsellik mekanizmaları olsa da, temel COM mekanizması kullanmaktır `IUnknown` adlı bir yöntem [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)).

Her arabirimi türetilir `IUnknown`her arabirim uygulaması vardır. Bu nedenle `QueryInterface`. Uygulama ne olursa olsun, bu yöntem bir işaretçi kendisine çağıran istediği arabirimi Laboratuvardaki kullanarak nesneyi sorgular. Nesne bu arabirimi destekliyorsa `QueryInterface` arabirim işaretçisi alır. Ayrıca çağrılırken `AddRef`. Aksi takdirde e_noınterface hata kodu döndürür.

Uyma gerekir Not [başvuru sayımı](../atl/reference-counting.md) kuralları her zaman. Eğer `Release` başvuru sayısı sıfır değerine düşürmek için bir arabirim işaretçisi üzerinde Bu işaretçi yeniden kullanmamanız gerekir. Bazen bir nesnenin zayıf bir başvuru elde etmeniz gerekebilir (diğer bir deyişle, başvuru sayısını artırmadan arabirimlerinden birini bir işaretçi alma iyi olabilir), ancak bunu çağırarak yapmak için kabul edilebilir değil `QueryInterface` ardından `Release`. Böyle bir şekilde elde edilen işaretçi, geçersiz ve kullanılmamalıdır. Bu daha kolay olduğunda görünür olur [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) bu makrosu tanımlama bulma başvuru sayım hataları için kullanışlı bir yol, bu nedenle, tanımlanır.

## <a name="see-also"></a>Ayrıca bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[QueryInterface: Bir nesne içinde gezinme](/windows/desktop/com/queryinterface--navigating-in-an-object)
