---
title: ATL AXHost kullanarak ActiveX denetimleri barındırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2T class
- Calendar control (ActiveX), hosting with ATL AXHost
- Calendar control (ActiveX)
- ActiveX controls [C++], hosting
- hosting ActiveX controls
- AXHost method
ms.assetid: 2c1200ec-effb-4814-820a-509519699468
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e26fd9e80b96c2b0196e3fd0e11b9c97f0f3bff3
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027212"
---
# <a name="hosting-activex-controls-using-atl-axhost"></a>ATL AXHost kullanarak ActiveX denetimleri barındırma
Bu konudaki örnek, AXHost oluşturma ve çeşitli ATL işlevleri kullanarak bir ActiveX denetimini barındırmak nasıl gösterir. Ayrıca bir erişim denetimi ve havuz olaylarını nasıl gösterir (kullanarak [Idispeventımpl](../atl/reference/idispeventimpl-class.md)) denetiminden barındırılır. Örnek, bir ana penceresinde veya bir alt pencere takvim denetimini barındırır.  
  
 USE_METHOD simgesinin tanımı dikkat edin. 1 ile 8 arasında değiştirmek için bu simge değerini değiştirebilirsiniz. Sembol değeri, denetimin nasıl oluşturulur belirler:  
  
-   USE_METHOD, konak kılabileceği bir pencere oluşturma çağrısı değerler çift sayılı için ve bir denetim ana bilgisayara dönüştürür. Tek sayılı değerler için kod ana bilgisayar gibi davranan bir alt pencere oluşturur.  
  
-   USE_METHOD değerleri 1 ile 4 arasında erişim denetimi ve olaylarını indirme arama gerçekleştirilir, ayrıca ana bilgisayar oluşturur. 8 ile 5 arasındaki değerleri arabirimleri için ana bilgisayar sorgulama ve havuz bağlama.  
  
Bir özeti aşağıda verilmiştir:  
  
|USE_METHOD|Ana bilgisayar|Erişimi denetlemek ve olay indirme|Gösterilen işlevi|  
|-----------------|----------|--------------------------------------|---------------------------|  
|1.|Alt pencere|Bir adım|CreateControlLicEx|  
|2|Ana pencere|Bir adım|AtlAxCreateControlLicEx|  
|3|Alt pencere|Bir adım|CreateControlEx|  
|4|Ana pencere|Bir adım|AtlAxCreateControlEx|  
|5|Alt pencere|Birden çok adımı|CreateControlLic|  
|6|Ana pencere|Birden çok adımı|AtlAxCreateControlLic|  
|7|Alt pencere|Birden çok adımı|CreateControl|  
|8|Ana pencere|Birden çok adımı|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim kapsamı SSS](../atl/atl-control-containment-faq.md)   
 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)   
 [AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)   
 [AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [CAxWindow2T sınıfı](../atl/reference/caxwindow2t-class.md)   
 [IAxWinHostWindowLic Arabirimi](../atl/reference/iaxwinhostwindowlic-interface.md)

