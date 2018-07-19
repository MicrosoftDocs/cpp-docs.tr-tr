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
ms.openlocfilehash: b3227ebd4767bd7639bb5e5d8d5a1c73e26079dc
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953427"
---
# <a name="queryinterface"></a>QueryInterface
Bir nesne express statik olarak (Bu örneği oluşturulmadan) sağladığı işlevsellik mekanizmaları olsa da, temel COM mekanizması kullanmaktır `IUnknown` adlı bir yöntem [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 Her arabirimi türetilir `IUnknown`her arabirim uygulaması vardır. Bu nedenle `QueryInterface`. Uygulama ne olursa olsun, bu yöntem bir işaretçi kendisine çağıran istediği arabirimi Laboratuvardaki kullanarak nesneyi sorgular. Nesne bu arabirimi destekliyorsa `QueryInterface` arabirim işaretçisi alır. Ayrıca çağrılırken `AddRef`. Aksi takdirde e_noınterface hata kodu döndürür.  
  
 Uyma gerekir Not [başvuru sayımı](../atl/reference-counting.md) kuralları her zaman. Eğer `Release` başvuru sayısı sıfır değerine düşürmek için bir arabirim işaretçisi üzerinde Bu işaretçi yeniden kullanmamanız gerekir. Bazen bir nesnenin zayıf bir başvuru elde etmeniz gerekebilir (diğer bir deyişle, başvuru sayısını artırmadan arabirimlerinden birini bir işaretçi alma iyi olabilir), ancak bunu çağırarak yapmak için kabul edilebilir değil `QueryInterface` ardından `Release`. Böyle bir şekilde elde edilen işaretçi, geçersiz ve kullanılmamalıdır. Bu daha kolay olduğunda görünür olur [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) bu makrosu tanımlama bulma başvuru sayım hataları için kullanışlı bir yol, bu nedenle, tanımlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM'a giriş](../atl/introduction-to-com.md)   
 [QueryInterface: bir nesne içinde gezinme](http://msdn.microsoft.com/library/windows/desktop/ms687230)

