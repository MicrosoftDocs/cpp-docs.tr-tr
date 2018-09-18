---
title: QueryInterface | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c361bc9510c610f2004af9f09c061d6f4b8b8cd2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057456"
---
# <a name="queryinterface"></a>QueryInterface

Bir nesne express statik olarak (Bu örneği oluşturulmadan) sağladığı işlevsellik mekanizmaları olsa da, temel COM mekanizması kullanmaktır `IUnknown` adlı bir yöntem [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)).

Her arabirimi türetilir `IUnknown`her arabirim uygulaması vardır. Bu nedenle `QueryInterface`. Uygulama ne olursa olsun, bu yöntem bir işaretçi kendisine çağıran istediği arabirimi Laboratuvardaki kullanarak nesneyi sorgular. Nesne bu arabirimi destekliyorsa `QueryInterface` arabirim işaretçisi alır. Ayrıca çağrılırken `AddRef`. Aksi takdirde e_noınterface hata kodu döndürür.

Uyma gerekir Not [başvuru sayımı](../atl/reference-counting.md) kuralları her zaman. Eğer `Release` başvuru sayısı sıfır değerine düşürmek için bir arabirim işaretçisi üzerinde Bu işaretçi yeniden kullanmamanız gerekir. Bazen bir nesnenin zayıf bir başvuru elde etmeniz gerekebilir (diğer bir deyişle, başvuru sayısını artırmadan arabirimlerinden birini bir işaretçi alma iyi olabilir), ancak bunu çağırarak yapmak için kabul edilebilir değil `QueryInterface` ardından `Release`. Böyle bir şekilde elde edilen işaretçi, geçersiz ve kullanılmamalıdır. Bu daha kolay olduğunda görünür olur [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) bu makrosu tanımlama bulma başvuru sayım hataları için kullanışlı bir yol, bu nedenle, tanımlanır.

## <a name="see-also"></a>Ayrıca Bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[QueryInterface: bir nesne içinde gezinme](/windows/desktop/com/queryinterface--navigating-in-an-object)

