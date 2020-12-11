---
description: 'Daha fazla bilgi edinin: QueryInterface'
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: b22163c9e69bd5573f8e6060df0457862813c366
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159183"
---
# <a name="queryinterface"></a>QueryInterface

Bir nesnenin statik olarak sağladığı işlevselliği ifade eden mekanizmalar olsa da, temel COM mekanizması `IUnknown` [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))olarak adlandırılan yöntemi kullanmaktır.

Her arabirim öğesinden türetilir `IUnknown` , bu nedenle her arabirim bir uygulamasına sahiptir `QueryInterface` . Uygulamadan bağımsız olarak, bu yöntem, çağıranın bir işaretçi istediği arabirimin IID 'sini kullanarak bir nesneyi sorgular. Nesne bu arabirimi destekliyorsa, `QueryInterface` arabirimine bir işaretçi alır, ayrıca öğesini de çağırır `AddRef` . Aksi takdirde, E_NOINTERFACE hata kodu döndürür.

[Başvuru sayma](../atl/reference-counting.md) kurallarına her zaman uymayı unutmayın. `Release`Başvuru sayısını sıfıra düşürmek için bir arabirim İşaretçisinde çağrı yaparsanız, bu işaretçiyi tekrar kullanmamalısınız. Bazen bir nesneye zayıf bir başvuru edinmeniz gerekebilir (yani, başvuru sayısını arttırmadan arabirimlerinden birine bir işaretçi elde etmek isteyebilirsiniz), ancak bunu tarafından çağırarak bunu yapmak kabul edilemez `QueryInterface` `Release` . Bu tür bir şekilde alınan işaretçi geçersizdir ve kullanılmamalıdır. [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) tanımlandığında bu daha kolay görünür hale gelir. bu nedenle, bu makroyu tanımlamak, başvuru sayma hatalarını bulmanın yararlı bir yoludur.

## <a name="see-also"></a>Ayrıca bkz.

[COM'a Giriş](../atl/introduction-to-com.md)<br/>
[QueryInterface: bir nesnede gezinme](/windows/win32/com/queryinterface--navigating-in-an-object)
