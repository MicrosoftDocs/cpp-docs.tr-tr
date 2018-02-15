---
title: "Birden çok çift arabirimler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- multiple dual interfaces
- COM_INTERFACE_ENTRY2 macro
- dual interfaces, exposing multiple
- multiple dual interfaces, exposing with ATL
- IDispatchImpl class, multiple dual interfaces
- COM_INTERFACE_ENTRY_IID macro
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01d87164439a4128ff6205ea6bc3ee3d9cc5573a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="multiple-dual-interfaces"></a>Birden çok çift arabirimler
Çift arabirim (diğer bir deyişle, vtable ve geç bağlama, böylece sınıf kullanılabilir C++ yanı sıra komut dosyası dili yapma esnekliği) avantajları birleştirmek isteyebilirsiniz birden çok devralma teknikleri ile.  
  
 Tek bir COM nesnesi üzerinde birden çok çift arabirimler kullanıma mümkün olsa da, önerilmez. Birden çok çift arabirimler varsa olmalıdır tek `IDispatch` sunulan arabirimi. Bu durumda olduğundan emin olmak teknikleri cezaları işlevi ya da daha fazla kod karmaşıklığı kaybı gibi uygulayın. Bu yaklaşım dikkate Geliştirici dikkatle olumlu ve olumsuz tartmanız gerekir.  
  
## <a name="exposing-a-single-idispatch-interface"></a>Tek bir IDispatch arabirimi gösterme  
 Tek bir nesne üzerinde birden çok çift arabirimler iki veya daha fazla özelleştirmeleri türetme tarafından kullanıma mümkündür `IDispatchImpl`. Bununla birlikte, istemcilerin sorgulamak için izin verirseniz `IDispatch` arabirimi, kullanması gerekecektir [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) makrosu (veya [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid))) kullanılmak üzere hangi temel sınıf belirtmek için uygulaması `IDispatch`.  
  
 [!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]  
  
 Çünkü tek `IDispatch` arabirimi gösterilir, yalnızca nesnelerinizi aracılığıyla erişebilirsiniz istemcileri `IDispatch` arabirimi edemeyecek yöntemleri veya diğer bir arabirimi özelliklerinde erişmek.  
  
## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>Birden çok çift arabirimler tek IDispatch uygulamasına birleştirme  
 ATL sağlamaz herhangi bir destek, tek bir uygulama içinde birden çok çift arabirimler birleştirme `IDispatch`. Ancak, ayrı bir birleşimini içerir şablonlu bir sınıf oluşturma gibi arabirimleri, el ile birleştirme için birkaç bilinen yaklaşım vardır `IDispatch` gerçekleştirmek için yeni bir nesne oluşturma arabirimleri `QueryInterface` işlevi veya kullanarak bir TypeInfo tabanlı bir uygulama oluşturmak için iç içe geçmiş nesnelerin `IDispatch` arabirimi.  
  
 Bu yaklaşım olası ad çakışmalarının yanı sıra kod karmaşıklığı ve bakımı sorunlarınız. Birden çok çift arabirimler oluşturma önerilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çift Arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)

