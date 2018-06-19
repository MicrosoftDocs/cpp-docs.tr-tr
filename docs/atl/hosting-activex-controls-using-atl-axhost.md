---
title: ATL AXHost kullanarak ActiveX denetimlerini barındırma | Microsoft Docs
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
ms.openlocfilehash: 5057a077e8e778fa3d943b736d51d19af8f60fc6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356259"
---
# <a name="hosting-activex-controls-using-atl-axhost"></a>ATL AXHost kullanarak ActiveX denetimlerini barındırma
Bu konudaki örnek AXHost oluşturma ve çeşitli ATL işlevleri kullanarak bir ActiveX denetimini barındırmak nasıl göstermektedir. Ayrıca denetim ve havuz olayları erişmek nasıl gösterir (kullanarak [IDispEventImpl](../atl/reference/idispeventimpl-class.md)) barındırılan denetiminden. Örnek ana penceresinde veya alt pencere Takvim denetimi barındırır.  
  
 Tanımını fark `USE_METHOD` simgesi. 1 ile 8 arasında değiştirmek için bu simge değerini değiştirebilirsiniz. Simgenin değerini denetimi nasıl oluşturulacak belirler:  
  
-   Değerler çift sayılı için `USE_METHOD`, ana bilgisayar alt sınıfların bir pencere oluşturma çağrısı ve bir denetim ana bilgisayara dönüştürür. Tek sayılı değerleri için bir ana bilgisayar gibi davranan bir alt pencere kodu oluşturur.  
  
-   Değerler için `USE_METHOD` 1 ile 4 arasında denetime erişme ve olayları indirme da ana bilgisayar oluşturur çağrısında gerçekleştirilir. Değerler 5 ile 8 arasında arabirimleri için ana bilgisayarı sorgulamak ve havuz kanca.  
  
 Bir özeti aşağıda verilmiştir:  
  
|USE_METHOD|Ana bilgisayar|Erişimi denetlemek ve olay indirme|Gösterilen işlevi|  
|-----------------|----------|--------------------------------------|---------------------------|  
|1.|Alt pencere|Bir adım|CreateControlLicEx|  
|2|Ana penceresi|Bir adım|AtlAxCreateControlLicEx|  
|3|Alt pencere|Bir adım|CreateControlEx|  
|4|Ana penceresi|Bir adım|AtlAxCreateControlEx|  
|5|Alt pencere|Birden çok adımı|CreateControlLic|  
|6|Ana penceresi|Birden çok adımı|AtlAxCreateControlLic|  
|7|Alt pencere|Birden çok adımı|CreateControl|  
|8|Ana penceresi|Birden çok adımı|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim kapsamı SSS](../atl/atl-control-containment-faq.md)   
 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)   
 [AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)   
 [AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [CAxWindow2T sınıfı](../atl/reference/caxwindow2t-class.md)   
 [IAxWinHostWindowLic Arabirimi](../atl/reference/iaxwinhostwindowlic-interface.md)

