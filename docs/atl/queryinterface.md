---
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: 37bb7a8c7fef963f340704561e24e33cc36707f3
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298642"
---
# <a name="queryinterface"></a>QueryInterface

Bir nesnenin statik olarak sağladığı işlevselliği ifade edebilir (örneği oluşturulmadan önce), temel COM mekanizması, [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))adlı `IUnknown` yöntemini kullanmaktır.

Her arabirim `IUnknown`türetilir, bu nedenle her arabirim bir `QueryInterface`uygulamasına sahiptir. Uygulamadan bağımsız olarak, bu yöntem, çağıranın bir işaretçi istediği arabirimin IID 'sini kullanarak bir nesneyi sorgular. Nesne bu arabirimi destekliyorsa, `QueryInterface` arabirime yönelik bir işaretçi alır ve ayrıca `AddRef`çağırır. Aksi takdirde, E_NOINTERFACE hata kodu döndürür.

[Başvuru sayma](../atl/reference-counting.md) kurallarına her zaman uymayı unutmayın. Başvuru sayısını sıfıra düşürmek için bir arabirim İşaretçisinde `Release` çağırırsanız, bu işaretçiyi tekrar kullanmamalısınız. Bazen bir nesneye zayıf bir başvuru edinmeniz gerekebilir (yani, başvuru sayısını arttırmadan arabirimlerinden birine yönelik bir işaretçi elde etmek isteyebilirsiniz), ancak `QueryInterface` ve ardından `Release`çağırarak bunu yapmak için kabul edilebilir değildir. Bu tür bir şekilde alınan işaretçi geçersizdir ve kullanılmamalıdır. [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) tanımlandığında bu daha kolay görünür hale gelir. bu nedenle, bu makroyu tanımlamak, başvuru sayma hatalarını bulmanın yararlı bir yoludur.

## <a name="see-also"></a>Ayrıca bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[QueryInterface: bir nesnede gezinme](/windows/win32/com/queryinterface--navigating-in-an-object)
