---
title: Bir CStatusBarCtrl nesnesinin bölümlerini başlatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89cea1516924530f821003affd96e2848687882b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>Bir CStatusBarCtrl Nesnesinin Bölümlerini Başlatma
Varsayılan olarak, bir durum çubuğu ayrı bölmeleri kullanarak durum bilgilerini görüntüler. Bunlardan (parçaları olarak da bilinir) bir metin dizesi, bir simge ya da her ikisini de içerebilir.  
  
 Kullanım [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) kaç bölümleri ve uzunluk tanımlamak için durum çubuğunu sahip olur. Durum çubuğu bölümlerini oluşturduktan sonra çağrı yapmak [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) ve [SetIcon](../mfc/reference/cstatusbarctrl-class.md#seticon) metin ya da durum çubuğunda belirli bir kısmını simgesi ayarlamak için. Bölümü başarıyla ayarladıktan sonra denetim otomatik olarak çizilir.  
  
 Var olan aşağıdaki örnek başlatır `CStatusBarCtrl` nesne (`m_StatusBarCtrl`) dört bölmeleri içeren ve ardından ikinci bölümünde bir simge (IDI_ICON1) ve bazı metin ayarlar.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]  
  
 Modunu ayarlama hakkında daha fazla bilgi için bir `CStatusBarCtrl` basit, bkz: nesnesine [CStatusBarCtrl nesnesinin modunu ayarlama](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStatusBarCtrl kullanma](../mfc/using-cstatusbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

