---
title: QueryInterface | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: QueryInterface
dev_langs: C++
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5714eab684066e74a6d56144d915460b4312f4c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="queryinterface"></a>QueryInterface
Tarafından bir nesne express statik olarak (Bu örneği oluşturulmadan önce) sağladığı işlevselliğe mekanizmaları olsa da, temel COM mekanizması kullanmaktır **IUnknown** adlı bir yöntem [QueryInterface ](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 Her arabirimi türetilir **IUnknown**, her arabirim uygulaması nedenle `QueryInterface`. Uygulaması bağımsız olarak, bu yöntem için arayan bir işaretçi istediği arabirimi IID kullanılarak bir nesneyi sorgular. Nesne bu arabirim destekliyorsa `QueryInterface` de çağrılırken arayüzü için bir işaretçi alır `AddRef`. Aksi takdirde, döndürür **E_NOINTERFACE** hata kodu.  
  
 Uyma gerekir Not [başvuru sayımı](../atl/reference-counting.md) kuralları her zaman. Çağırırsanız **sürüm** başvuru sayısı sıfır düşürmek için bir arabirim işaretçisi üzerinde bu işaretçiyi yeniden kullanmamalısınız. Bazen bir nesneye zayıf bir başvuru elde etmeniz gerekebilir (diğer bir deyişle, başvuru sayımı artırmadan gösteren bir işaretçi arabirimlerinden birini elde etmek ister misiniz), ancak bunu çağırarak yapmak için kabul edilebilir değil `QueryInterface` arkasından  **Yayın**. Bu tür bir şekilde elde işaretçi geçersiz ve kullanılmamalıdır. Bu daha kolay ne zaman görünür olur [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) tanımlanır, bu makrosu tanımlama bulma başvuru sayım hataları için kullanışlı bir yol gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM giriş](../atl/introduction-to-com.md)   
 [QueryInterface: bir nesneyi gezinme](http://msdn.microsoft.com/library/windows/desktop/ms687230)

