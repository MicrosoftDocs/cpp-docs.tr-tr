---
title: Rebar denetimleri ve bantları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1fac5f83f19fab37604a14e239cf505891c737f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349857"
---
# <a name="rebar-controls-and-bands"></a>Rebar Denetimleri ve Bantları
Alt pencereler, ortak iletişim kutusu denetimleri, menüler, araç çubukları ve benzeri için kapsayıcı olarak hareket edecek bir rebar denetimi ana amacı budur. Bu kapsama bir "bant." kavramı tarafından desteklenir Her rebar bant Mandal çubuğu, bir bit eşlem, bir metin etiketi ve alt pencere herhangi bir birleşimini içerebilir.  
  
 Sınıf `CReBarCtrl` almak için kullanın ve işlemek, bilgi belirli rebar bant için çok sayıda üye işlevleri vardır:  
  
-   [GetBandCount](../mfc/reference/crebarctrl-class.md#getbandcount) rebar denetiminde geçerli Bantların sayısı alır.  
  
-   [GetBandInfo](../mfc/reference/crebarctrl-class.md#getbandinfo) başlatır bir **REBARBANDINFO** belirtilen bant bilgileriyle yapısı. Var olan bir karşılık gelen [SetBandInfo](../mfc/reference/crebarctrl-class.md#setbandinfo) üye işlevi.  
  
-   [GetRect](../mfc/reference/crebarctrl-class.md#getrect) belirtilen bant sınırlayıcı dikdörtgenini alır.  
  
-   [GetRowCount](../mfc/reference/crebarctrl-class.md#getrowcount) bir rebar denetiminde bant satır sayısını alır.  
  
-   [IDToIndex](../mfc/reference/crebarctrl-class.md#idtoindex) belirtilen bant dizinini alır.  
  
-   [GetBandBorders](../mfc/reference/crebarctrl-class.md#getbandborders) bir bant Kenarlıklar alır.  
  
 İşleme ek olarak, belirli rebar bantları üzerinde çalışmasına izin veren birkaç üye işlevleri sağlanır.  
  
 [InsertBand](../mfc/reference/crebarctrl-class.md#insertband) ve [DeleteBand](../mfc/reference/crebarctrl-class.md#deleteband) ekleme ve rebar bantları kaldırma. [MinimizeBand](../mfc/reference/crebarctrl-class.md#minimizeband) ve [MaximizeBand](../mfc/reference/crebarctrl-class.md#maximizeband) belirli rebar bant boyutunu etkiler. [MoveBand](../mfc/reference/crebarctrl-class.md#moveband) belirli rebar bant dizinini değiştirir. [ShowBand](../mfc/reference/crebarctrl-class.md#showband) gösterir veya rebar bant kullanıcıdan gizler.  
  
 Aşağıdaki örnek, bir araç bant ekleme gösterir (`m_wndToolBar`) var olan bir rebar denetimi (`m_wndReBar`). Bant başlatarak açıklanan `rbi` yapısı ve ardından çağırma `InsertBand` üye fonksiyonu:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CReBarCtrl kullanma](../mfc/using-crebarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

