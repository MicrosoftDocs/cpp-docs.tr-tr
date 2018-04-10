---
title: IDispEventSimpleImpl (ATL) kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDispEventSimpleImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed21c862d61686e86efd684a6e88795e4b7bbe51
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-idispeventsimpleimpl"></a>IDispEventSimpleImpl kullanma
Kullanırken `IDispEventSimpleImpl` olayları işlemek için yapmanız gerekir:  
  
-   Sınıfından türetilen [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md).  
  
-   Bir olay havuz eşlemesi sınıfınıza ekleyin.  
  
-   Tanımlamak [_ATL_FUNC_INFO](../atl/reference/atl-func-info-structure.md) olayları tanımlayan yapıları.  
  
-   Olay iç havuz kullanarak eşleme girişleri eklemek [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info) makrosu.  
  
-   İşlemede ilgilenen yöntemleri uygulayın.  
  
-   Öneri ve olay kaynağı unadvise.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl işleneceğini gösterir **DocumentChange** olay harekete Word tarafından **uygulama** nesnesi. Bu olay bir yöntem olarak tanımlanan **ApplicationEvents** görüntüleme arabirimi.  
  
 Örnek kaynaklı [ATLEventHandling örnek](../visual-cpp-samples.md).  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 Örnek kullanır `#import` Word tür kitaplığından gereken üstbilgi dosyaları oluşturmak için. Word'ün diğer sürümleri bu örneği kullanmak istiyorsanız, doğru mso dll dosyası belirtmeniz gerekir. Örneğin, Office 2000 mso9.dll ve mso.dll OfficeXP sağlar. Bu kod stdafx.h basitleştirilir:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventsimpleimpl_1.h)]  
  
 Yalnızca gerçekten bu örnekte kullanılan tür kitaplığından Word CLSID bilgilerdir **uygulama** nesne ve Laboratuvardaki Kimliğini **ApplicationEvents** arabirimi. Bu bilgiler yalnızca derleme zamanında kullanılır.  
  
 Aşağıdaki kod Simple.h içinde görüntülenir. İlgili kodu açıklamaları tarafından belirtilir:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/cpp/using-idispeventsimpleimpl_2.h)]  
  
 Aşağıdaki kodu Simple.cpp verilmiştir:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/cpp/using-idispeventsimpleimpl_3.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay işleme](../atl/event-handling-and-atl.md)   
 [ATLEventHandling örnek](../visual-cpp-samples.md)

