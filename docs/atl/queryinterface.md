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
ms.openlocfilehash: cde92ee56e51a86acbfb7e459571291bc3cae76c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="queryinterface"></a>QueryInterface
Tarafından bir nesne express statik olarak (Bu örneği oluşturulmadan önce) sağladığı işlevselliğe mekanizmaları olsa da, temel COM mekanizması kullanmaktır **IUnknown** adlı bir yöntem [QueryInterface ](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 Her arabirimi türetilir **IUnknown**, her arabirim uygulaması nedenle `QueryInterface`. Uygulaması bağımsız olarak, bu yöntem için arayan bir işaretçi istediği arabirimi IID kullanılarak bir nesneyi sorgular. Nesne bu arabirim destekliyorsa `QueryInterface` de çağrılırken arayüzü için bir işaretçi alır `AddRef`. Aksi takdirde, döndürür **E_NOINTERFACE** hata kodu.  
  
 Uyma gerekir Not [başvuru sayımı](../atl/reference-counting.md) kuralları her zaman. Çağırırsanız **sürüm** başvuru sayısı sıfır düşürmek için bir arabirim işaretçisi üzerinde bu işaretçiyi yeniden kullanmamalısınız. Bazen bir nesneye zayıf bir başvuru elde etmeniz gerekebilir (diğer bir deyişle, başvuru sayımı artırmadan gösteren bir işaretçi arabirimlerinden birini elde etmek ister misiniz), ancak bunu çağırarak yapmak için kabul edilebilir değil `QueryInterface` arkasından  **Yayın**. Bu tür bir şekilde elde işaretçi geçersiz ve kullanılmamalıdır. Bu daha kolay ne zaman görünür olur [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) tanımlanır, bu makrosu tanımlama bulma başvuru sayım hataları için kullanışlı bir yol gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM giriş](../atl/introduction-to-com.md)   
 [QueryInterface: bir nesneyi gezinme](http://msdn.microsoft.com/library/windows/desktop/ms687230)

