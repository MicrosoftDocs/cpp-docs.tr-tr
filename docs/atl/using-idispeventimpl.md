---
title: IDispEventImpl (ATL) kullanarak | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f787fac05e95fff8a974692c3e6fca24561ed222
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-idispeventimpl"></a>IDispEventImpl kullanma
Kullanırken `IDispEventImpl` olayları işlemek için yapmanız gerekir:  
  
-   Sınıfından türetilen [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
-   Bir olay havuz eşlemesi sınıfınıza ekleyin.  
  
-   Olay iç havuz kullanarak eşleme girişleri eklemek [SINK_ENTRY](reference/composite-control-macros.md#sink_entry) veya [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) makrosu.  
  
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
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]  
  
 Aşağıdaki kod NotSoSimple.h içinde görüntülenir. İlgili kodu açıklamaları tarafından belirtilir:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay işleme](../atl/event-handling-and-atl.md)   
 [ATLEventHandling örnek](../visual-cpp-samples.md)

