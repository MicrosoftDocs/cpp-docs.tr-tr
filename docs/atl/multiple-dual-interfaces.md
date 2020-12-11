---
description: 'Daha fazla bilgi edinin: birden çok çift arabirim'
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
ms.openlocfilehash: d90c0176b3165cc0e5b976a29ec58b58fd3a7a56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159421"
---
# <a name="multiple-dual-interfaces"></a>Birden çok çift arabirim

Bir çift arabirimin avantajlarını (yani, hem vtable hem de geç bağlamanın esnekliği) birleştirmek isteyebilirsiniz. bu sayede, sınıfı birden çok devralmanın teknikleriyle C++ ve C++ için kullanılabilir hale getirebilirsiniz.

Birden çok çift arabirimi tek bir COM nesnesinde kullanıma sunmak mümkün olsa da önerilmez. Birden çok çift arabirim varsa, yalnızca bir `IDispatch` arabirim kullanıma sunulmalıdır. Bunun, işlevin kaybı veya daha fazla kod karmaşıklığı gibi bir durum olduğundan emin olmak için kullanabileceğiniz teknikler. Bu yaklaşımı ele alarak oluşan geliştirici, olumlu ve olumsuz yönleri dikkatle göstermelidir.

## <a name="exposing-a-single-idispatch-interface"></a>Tek bir IDispatch arabirimini gösterme

İki veya daha fazla uzmanlıklardan türeterek tek bir nesne üzerinde birden çok çift arabirimi göstermek mümkündür `IDispatchImpl` . Bununla birlikte, istemcilerin arabirim için sorgulamasına izin verirseniz `IDispatch` , uygulamasının uygulanması için hangi temel sınıfın kullanılacağını belirtmek üzere [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) makrosunu (veya [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid))) kullanmanız gerekir `IDispatch` .

[!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]

Yalnızca bir `IDispatch` arabirim kullanıma sunulduğundan, nesnelerinize yalnızca arabirim aracılığıyla erişebilen istemciler `IDispatch` başka bir arabirimdeki yöntemlere veya özelliklere erişemez.

## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>Birden çok çift arabirimi IDispatch 'in tek bir uygulamasında birleştirme

ATL birden çok çift arabirimi tek bir uygulamasında birleştirmek için herhangi bir destek sağlamaz `IDispatch` . Ancak, ayrı arabirimlerin birleşimini içeren bir şablonlu sınıf oluşturma `IDispatch` , işlevi gerçekleştirmek için yeni bir nesne oluşturma `QueryInterface` veya arabirimi oluşturmak için iç içe geçmiş nesnelerin TypeInfo tabanlı bir uygulamasını kullanma gibi, arabirimleri el ile birleştiren birkaç bilinen yaklaşım vardır `IDispatch` .

Bu yaklaşımlar, olası ad alanı çarpışmalarının yanı sıra kod karmaşıklığı ve bakım sorununa neden olabilir. Birden çok çift arabirim oluşturmanız önerilmez.

## <a name="see-also"></a>Ayrıca bkz.

[Çift arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)
