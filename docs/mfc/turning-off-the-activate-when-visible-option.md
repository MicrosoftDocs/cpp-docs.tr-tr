---
title: "Görünürken etkinleştir seçeneğini devre dışı kapatma | Microsoft Docs"
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
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25521d75921b377730a7f9afac71f2a60c055216
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="turning-off-the-activate-when-visible-option"></a>Görünürken Etkinleştir Seçeneğini Kapatma
Bir denetim iki temel durumlara sahiptir: etkin ve etkin değil. Geleneksel olarak, bu durumu denetimi bir pencere kaldı tarafından ayırt. Etkin bir denetim bir pencere vardı; Etkin olmayan denetimi belirtmiyor. Penceresiz etkinleştirme giriş, bu ayrım artık Evrensel değil, ancak birçok denetimleri için hala geçerlidir.  
  
 Genellikle bir ActiveX denetimi tarafından gerçekleştirilen başlatma geri kalanı ile karşılaştırıldığında, bir pencere oluşturma bir çok pahalı bir işlemdir. İdeal olarak, bir denetim onun penceresi kesinlikle gerekli kadar erteleme.  
  
 Çoğu denetim bir kapsayıcıda görünür tüm zaman etkin olması gerekmez. Genellikle, kullanıcı bunu (örneğin fareyle tıklatarak veya TAB tuşuna basarak) etkin olmasını gerektiren bir işlem gerçekleştirdiğinde kadar denetim devre dışı durumda kalabilir. Bir denetimi etkinleştirmek kapsayıcı gereken kadar devre dışı kalmasına neden için kaldırın **OLEMISC_ACTIVATEWHENVISIBLE** denetimin çeşitli bayrakları bayrağı:  
  
 [!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]  
  
 **OLEMISC_ACTIVATEWHENVISIBLE** bayrağı kapatılırsa otomatik olarak atlanmış **etkinleştirme görünürken** seçeneğini [denetim ayarlarını](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX sayfası Denetim oluşturduğunuzda Denetim Sihirbazı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri: İyileştirme](../mfc/mfc-activex-controls-optimization.md)

