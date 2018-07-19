---
title: ATL nedir denetim barındırma API'si? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- APIs [C++], hosting
- control-hosting API
- controls [ATL], hosting APIs
ms.assetid: 75b27e45-cfba-4950-aa35-96cc7d8da753
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2cc85c7ca47d5d1226ffc3089e01c0755ef6c6ac
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850560"
---
# <a name="what-is-the-atl-control-hosting-api"></a>ATL nedir denetim barındırma API'si?
ATL Denetim barındırma API'si, bir ActiveX denetimi kapsayıcısı görev yapacak bir pencere sağlar işlevler kümesi. Bu işlevlerin statik olabilir veya dinamik olarak kod kaynağı olarak kullanılabilir olduğu projenize bağlı ve ATL90.dll tarafından kullanıma sunulan. Denetim barındırma işlevleri, aşağıdaki tabloda listelenmiştir.  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|Bir konak nesnesi oluşturur, sağlanan penceresine bağlanır ve ardından varolan bir denetimi ekler.|  
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|Bir konak nesnesi oluşturur, sağlanan penceresine bağlanır ve ardından Denetim yükler.|  
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve benzer şekilde belirtilen pencerede barındırır [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol).|  
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|Bir konak nesnesi oluşturur, sağlanan penceresine bağlanır ve ardından Denetim yükler (Ayrıca olay iç havuzları ayarlanmasına izin verir).|  
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve benzer şekilde belirtilen pencerede barındırır [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic).|  
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|İletişim kutusu kaynağı modsuz iletişim kutusu oluşturur ve pencere tanıtıcısını döndürür.|  
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|Kalıcı bir iletişim kutusu, iletişim kutusu kaynağı oluşturur.|  
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|Döndürür `IUnknown` arayüz işaretçisinden bir pencere içinde barındırılan bir denetim.|  
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|Döndürür `IUnknown` arayüz işaretçisinden bir konak nesnesi bağlı bir pencere.|  
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|Denetim barındırma kodunu başlatır.|  
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|Denetim barındırma kodunu başlamasını iptal eder.|  
  
 `HWND` İlk üç işlev parametrelerinde varolan pencereye (yaklaşık) herhangi bir türde olması gerekir. Bu üç işlevlerden herhangi birinin açıkça çağırırsanız (genellikle, gerekmez), zaten bir konak olarak hareket eden bir pencere için bir tanıtıcı geçmeyin (Bunu yaparsanız, var olan konak nesnesi serbest olmaz).  
  
 İlk yedi işlevlerini [zaman Atlaxwinınit](reference/composite-control-global-functions.md#atlaxwininit) örtük olarak.  
  
> [!NOTE]
>  Denetim barındırma API'si ActiveX denetimi kapsamasını ATL desteği temelini oluşturur. Ancak, yoktur genellikle yararlanın ya da tam ATL sarmalayıcı sınıflar kullanılmasını sağlamak için bu işlevler doğrudan çağırmak için pek gereksinim. Daha fazla bilgi için [hangi ATL sınıfları kolaylaştırmak ActiveX denetimi kapsamasını](which-atl-classes-facilitate-activex-control-containment-q.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim kapsamı SSS](which-atl-classes-facilitate-activex-control-containment-q.md)
