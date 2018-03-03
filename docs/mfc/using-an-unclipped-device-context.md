---
title: "Kesilmemiş bir cihaz bağlamı kullanma | Microsoft Docs"
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
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae095b59b07132bd7e4c6892b8e58d9e69fb39c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-unclipped-device-context"></a>Kesilmemiş Bir Cihaz Bağlamı Kullanma
Denetim dışında kendi istemci dikdörtgeni boyamak değil kesinlikle emin olduğunuzda çağrısı devre dışı bırakarak küçük ancak algılanabilir hızı kazanç sağlarsınız `IntersectClipRect` tarafından yapılan `COleControl`. Bunu yapmak için kaldırmak **clipPaintDC** tarafından döndürülen bayrakları kümesinden bayrağı [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Örneğin:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]  
  
 Seçerseniz bu bayrağı kaldırmak için kodu otomatik olarak oluşturulan **kesilmemiş cihaz bağlamı** seçeneği [denetim ayarlarını](../mfc/reference/control-settings-mfc-activex-control-wizard.md) , MFC ActiveX Denetim Sihirbazı ile denetiminizi oluştururken, sayfa.  
  
 Penceresiz etkinleştirme kullanıyorsanız, bu en iyi duruma getirme bir etkisi yoktur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri: İyileştirme](../mfc/mfc-activex-controls-optimization.md)

