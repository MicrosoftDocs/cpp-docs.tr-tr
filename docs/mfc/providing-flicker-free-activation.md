---
title: "Titreşimsiz etkinleştirme sağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f98cc77ecc11f2b3ea07352e48c1e6a096125300
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="providing-flicker-free-activation"></a>Titreşimsiz Etkinleştirme Sağlama
Denetiminiz kendisini aynı etkin ve etkin durumda çizer (ve penceresiz etkinleştirme kullanmaz varsa), çizim işlemleri ve etkin olmayan arasında geçiş yaparken, normal olarak ortaya eşlik eden visual titreşimi çıkarabilirsiniz ve etkin durumları. Bunu yapmak için dahil **noFlickerActivate** tarafından döndürülen bayraklar kümesi bayrağı [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Örneğin:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]  
  
 Seçerseniz bu bayrak eklemek için kodu otomatik olarak oluşturulan **titreşimsiz etkinleştirme** seçeneği [denetim ayarlarını](../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfasında denetiminizi MFC ActiveX Denetim Sihirbazı ile oluştururken.  
  
 Penceresiz etkinleştirme kullanıyorsanız, bu en iyi duruma getirme bir etkisi yoktur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri: iyileştirme](../mfc/mfc-activex-controls-optimization.md)

