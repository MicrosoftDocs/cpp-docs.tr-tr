---
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: de2762cff3d697261e159336d866a5a7cb10fafa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492000"
---
# <a name="queryinterface"></a>QueryInterface

Bir nesnenin statik olarak sağladığı işlevselliği ifade eden mekanizmalar olsa da, temel com mekanizması `IUnknown` [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))olarak adlandırılan yöntemi kullanmaktır.

Her arabirim öğesinden `IUnknown`türetilir, bu nedenle her arabirim bir `QueryInterface`uygulamasına sahiptir. Uygulamadan bağımsız olarak, bu yöntem, çağıranın bir işaretçi istediği arabirimin IID 'sini kullanarak bir nesneyi sorgular. Nesne bu arabirimi `QueryInterface` destekliyorsa, arabirimine bir işaretçi alır, `AddRef`ayrıca öğesini de çağırır. Aksi takdirde, E_NOINTERFACE hata kodunu döndürür.

[Başvuru sayma](../atl/reference-counting.md) kurallarına her zaman uymayı unutmayın. Başvuru sayısını sıfıra `Release` düşürmek için bir arabirim İşaretçisinde çağrı yaparsanız, bu işaretçiyi tekrar kullanmamalısınız. Bazen bir nesneye zayıf bir başvuru edinmeniz gerekebilir (yani, başvuru sayısını arttırmadan arabirimlerinden birine bir işaretçi elde etmek isteyebilirsiniz), ancak bunu tarafından `QueryInterface` `Release`çağırarak bunu yapmak kabul edilemez. Bu tür bir şekilde alınan işaretçi geçersizdir ve kullanılmamalıdır. [_Atl_debug_ınterfaces](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) tanımlandığında bu daha kolay görünür hale gelir, bu nedenle bu makroyu tanımlamak, başvuru sayma hatalarını bulmanın yararlı bir yoludur.

## <a name="see-also"></a>Ayrıca bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[QueryInterface Bir nesne içinde gezinme](/windows/win32/com/queryinterface--navigating-in-an-object)
