---
title: "ATL nedir denetimi barındırma API? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- APIs [C++], hosting
- control-hosting API
- controls [ATL], hosting APIs
ms.assetid: 75b27e45-cfba-4950-aa35-96cc7d8da753
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e985ffd3b514feec81f4fee540a95792eb3658e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="what-is-the-atl-control-hosting-api"></a>ATL nedir denetimi barındırma API?
ATL denetimi barındırma bir ActiveX denetimi kapsayıcısı görev yapması herhangi bir penceresi sağlayan işlevler kümesi bir API'dir. Bu işlevler statik olarak olabilir veya dinamik kaynak kodu olarak kullanılabilir olduğu projenize bağlı ve ATL90.dll tarafından kullanıma sunulan. Denetimi barındırma işlevleri, aşağıdaki tabloda listelenmiştir.  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|Bir ana bilgisayar nesnesi oluşturur, sağlanan penceresine bağlanır ve sonra varolan bir denetim ekler.|  
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|Bir ana bilgisayar nesnesi oluşturur, sağlanan penceresine bağlanır ve sonra bir denetim yükler.|  
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|Lisanslı bir ActiveX denetimi oluşturur, bunu başlatır ve benzer belirtilen penceresinde barındıran [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol).|  
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|Bir ana bilgisayar nesnesi oluşturur, sağlanan penceresine bağlanır ve sonra bir denetim yükler (Ayrıca olay iç havuzları ayarlanmasına izin verir).|  
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|Lisanslı bir ActiveX denetimi oluşturur, bunu başlatır ve benzer belirtilen penceresinde barındıran [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic).|  
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|Kalıcı olmayan iletişim kutusu iletişim kaynağı oluşturur ve Pencere işleyicisini döndürür.|  
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|Modal bir iletişim kutusu iletişim kaynağı oluşturur.|  
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|Döndürür **IUnknown** bir pencerede barındırılan denetime arabirimi işaretçisi.|  
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|Döndürür **IUnknown** ana bilgisayar nesnesinin arabirim işaretçisi bağlı bir pencere.|  
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|Denetimi barındırma kodu başlatır.|  
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|Denetimi barındırma kodu uninitializes.|  
  
 `HWND` İlk üç işlevleri parametrelerinde mevcut bir pencere (neredeyse) herhangi bir türde olması gerekir. Bu üç işlevler hiçbirini açıkça çağırırsanız (tipik olarak sizin gerekmez), bir işleyici zaten bir konak olarak davranan bir pencere için geçmeyin (Bunu yaparsanız, var olan konak nesnesi boşaltılması olmaz).  
  
 İlk yedi işlevleri çağırmak [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) örtük olarak.  
  
> [!NOTE]
>  Denetimi barındırma API ActiveX denetimi kapsamasını desteği ATL'ın temelini oluşturur. Ancak, var. genellikle yararlanmak veya ATL'ın sarmalayıcı sınıflar tam kullanımını yaparsanız bu işlevler doğrudan çağırmak için pek gereksinim Daha fazla bilgi için bkz: [hangi ATL sınıfları kolaylaştırmak ActiveX denetimi kapsamasını](which-atl-classes-facilitate-activex-control-containment-q.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim kapsamı SSS](which-atl-classes-facilitate-activex-control-containment-q.md)
