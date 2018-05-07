---
title: Sekme ve sekme denetim öznitelikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [MFC], reference topics
- tab controls [MFC], attributes
- tabs [MFC]
- tabs [MFC], attributes
- CTabCtrl class [MFC], tab control attributes
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f925f8b6a5c522e22890ee2c1082ae8d709d2220
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="tabs-and-tab-control-attributes"></a>Sekme ve Sekme Denetimi Öznitelikleri
Görünümü ve davranışı Sekme denetimini oluşturan sekmelerinin üzerinde önemli denetiminiz ([CTabCtrl](../mfc/reference/ctabctrl-class.md)). Her sekme bir etiket, simge, bir öğesi durumu ve ilişkili bir uygulama tanımlı 32-bit değeri olabilir. Her sekme için simge, etiket veya her ikisi de görüntüleyebilirsiniz.  
  
 Ayrıca, her sekme öğesi üç olası durumlar olabilir: basıldığında basılmamış ya da vurgulanır. Bu durum yalnızca var olan bir sekme öğesi değiştirerek ayarlanabilir. Var olan bir sekme öğesini değiştirmek için bunu çağrısıyla almak [GetItem](../mfc/reference/ctabctrl-class.md#getitem), değişiklik `TCITEM` yapısı (özellikle **dwState** ve **dwStateMask** veri üyeleri ) ve ardından değiştirilen dönün `TCITEM` çağrısıyla yapısı [SetItem](../mfc/reference/ctabctrl-class.md#setitem). Tüm sekme öğeler öğesi durumları temizlemek gereken bir `CTabCtrl` nesne, çağırmaya [DeselectAll](../mfc/reference/ctabctrl-class.md#deselectall). Bu işlev tüm sekme öğeleri veya şu anda seçili dışındaki tüm öğeleri durumunu sıfırlar.  
  
 Aşağıdaki kod, tüm sekme öğeleri durumunu temizler ve üçüncü öğesinin durumunu değiştirir:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/cpp/tabs-and-tab-control-attributes_1.cpp)]  
  
 Sekme öznitelikleri hakkında daha fazla bilgi için bkz: [sekme ve sekme öznitelikleri](http://msdn.microsoft.com/library/windows/desktop/bb760550) Windows SDK. Sekme denetimine sekmeler ekleme hakkında daha fazla bilgi için bkz: [Sekme denetimine sekmeler ekleme](../mfc/adding-tabs-to-a-tab-control.md) bu konuda daha sonra.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTabCtrl kullanma](../mfc/using-ctabctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

