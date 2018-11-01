---
title: Birden çok çift arabirim
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- multiple dual interfaces
- COM_INTERFACE_ENTRY2 macro
- dual interfaces, exposing multiple
- multiple dual interfaces, exposing with ATL
- IDispatchImpl class, multiple dual interfaces
- COM_INTERFACE_ENTRY_IID macro
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
ms.openlocfilehash: c2ec6c89ab6f54dbcd7433a0f7fedcebd7962b6e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434743"
---
# <a name="multiple-dual-interfaces"></a>Birden çok çift arabirim

Çift arabirim (diğer bir deyişle, vtable ve geç bağlama, bu nedenle sınıf kullanılabilir C++ yanı sıra komut dosyası dilleri yapma esnekliği) avantajları birleştirmek isteyebilirsiniz birden çok devralma tekniklerle.

Tek bir COM nesne üzerinde birden çok çift arabirim kullanıma sunmak mümkün olsa da, önerilmez. Birden çok çift arabirim varsa, olmalıdır tek `IDispatch` kullanıma sunulan arabirimi. Bu durumda olduğundan emin olmak teknikleri yaptırımlara işlevi ya da daha fazla kod karmaşıklığı kaybı gibi uygulayın. Bu yaklaşım dikkate Geliştirici dikkatle olumlu ve olumsuz tartmanız gerekir.

## <a name="exposing-a-single-idispatch-interface"></a>Tek bir IDispatch arabirimi gösterme

Tek bir nesnede birden çok çift arabirim iki veya daha fazla uzmanlıkları türetme tarafından kullanıma sunmak mümkündür `IDispatchImpl`. Ancak, istemciler sorgulamak izin verirseniz `IDispatch` arabirimini kullanmanız gerekecek [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) makrosu (veya [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid))) kullanılmak üzere hangi temel sınıf belirtmek için uygulamasını `IDispatch`.

[!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]

Çünkü tek `IDispatch` arabirimi kullanıma sunulan, nesnelerinizi aracılığıyla yalnızca erişimi olan istemciler `IDispatch` arabirimi yöntemleri ya da herhangi bir arabirim özelliği erişmek mümkün olmayacaktır.

## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>Tek bir IDispatch uygulamasına birden çok çift arabirim birleştirme

ATL sağlamaz her türlü destek tek bir uygulama içinde birden çok çift arabirim birleştirmek için `IDispatch`. Ancak, ayrı bir birleşimini içeren bir şablonlu sınıf oluşturma gibi arabirimler, el ile birleştirme için birkaç bilinen yaklaşım vardır `IDispatch` gerçekleştirmek için yeni bir nesne oluşturma arabirimlerini `QueryInterface` işlevi veya kullanarak bir typeinfo tabanlı bir uygulama oluşturmak için iç içe geçmiş nesnelerin `IDispatch` arabirimi.

Bu yaklaşımların olası ad çakışmalarının yanı sıra kod karmaşıklığı ve bakımı ile ilgili sorunlar var. Birden çok çift arabirim oluşturmak önerilmez.

## <a name="see-also"></a>Ayrıca Bkz.

[Çift Arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)

