---
title: Araç ipuçları Cframewnd'den türetilmemiş Windows | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enabling tool tips [MFC]
- TOOLTIPTEXT structure [MFC]
- Help [MFC], tool tips for controls
- TTN_NEEDTEXT message [MFC]
- controls [MFC], tool tips
- handler functions [MFC], tool tips
ms.assetid: cad5ef0f-02e3-4151-ad0d-3d42e6932b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f187ae7e3d5d9dbe6441aa8e2ba0f7631fd5072
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956545"
---
# <a name="tool-tips-in-windows-not-derived-from-cframewnd"></a>CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları
Bu makale ailesi türetilmedi bir pencerede bulunan denetimler için etkinleştirme araç ipuçları kapsayan [CFrameWnd](../mfc/reference/cframewnd-class.md). Makaleyi [araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md) denetimler için araç ipuçları hakkında bilgi sağlayan bir `CFrameWnd`.  
  
 Bu makale ailesinde kapsanan konular şunlardır:  
  
-   [Araç İpuçlarını Etkinleştirme](../mfc/enabling-tool-tips.md)  
  
-   [Araç İpuçları için TTN_NEEDTEXT Bildirimini İşleme](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)  
  
-   [TOOLTIPTEXT yapısı](../mfc/tooltiptext-structure.md)  
  
 Araç ipuçları için düğmeler otomatik olarak görüntülenir ve bir ana pencerede bulunan diğer denetimleri türetilmiş `CFrameWnd`. Bunun nedeni, `CFrameWnd` için bir varsayılan işleyici sahip [TTN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760269) işler bildirim **TTN_NEEDTEXT** aracından bildirimleri ipucu denetimleriyle ilişkili denetimler.  
  
 Ancak, bu varsayılan işleyici ne zaman çağrılmaz **TTN_NEEDTEXT** bildirim değil bir pencerede denetimiyle ilişkili bir araç ipucunu denetimini gelen gönderilir bir `CFrameWnd`, bir iletişim kutusu veya bir form görünümü denetim gibi. Bu nedenle, sizin için bir işleyici işlevi sağlamak gerekli olan **TTN_NEEDTEXT** alt denetimler için araç ipuçları görüntülemek için uyarı iletisi.  
  
 Windows tarafından sağlanan varsayılan araç ipuçları [CWnd::EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips) ilişkili metin yok. Görüntülenecek araç ipucu metnini almak için **TTN_NEEDTEXT** araç ipucu penceresi yalnızca görüntülenmeden önce araç ipucu denetimin üst penceresine bildirim gönderilir. Bu ileti için bir değer atamak için hiçbir işleyici olup olmadığını *pszText* üyesi **TOOLTIPTEXT** yapısı, araç ipucu için görüntülenen metin olacaktır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araç İpuçları](../mfc/tool-tips.md)

