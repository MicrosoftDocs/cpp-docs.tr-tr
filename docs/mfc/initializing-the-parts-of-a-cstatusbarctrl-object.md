---
title: "Bir CStatusBarCtrl nesnesinin bölümlerini başlatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b713a46db13508df5ba80b21e3dfe938261eec65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

