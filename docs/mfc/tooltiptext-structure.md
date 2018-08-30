---
title: TOOLTIPTEXT yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TOOLTIPTEXT
dev_langs:
- C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f65b94294b3b3d55f9839dffa99a18be61c5639
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195990"
---
# <a name="tooltiptext-structure"></a>TOOLTIPTEXT Yapısı
Yazma, [araç ipucu bildirimi işleyicisi](../mfc/handling-ttn-needtext-notification-for-tool-tips.md), kullanmanız gereken **TOOLTIPTEXT** yapısı. Üyeleri **TOOLTIPTEXT** yapısı şunlardır:  
  
 `typedef struct {`  
  
 `NMHDR     hdr;        // required for all WM_NOTIFY messages`  
  
 `LPTSTR    lpszText;   // see below`  
  
 `TCHAR     szText[80]; // buffer for tool tip text`  
  
 `HINSTANCE hinst;      // see below`  
  
 `UINT      uflags;     // flag indicating how to interpret the`  
  
 `// idFrom member of the NMHDR structure`  
  
 `// that is included in the structure`  
  
 `} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;`  
  
 *HDR*  
 Metin gereken aracı tanımlar. Bu yapının ihtiyacınız olabilecek tek üyesi denetimin komut kimliğidir. Denetimin komut kimliği olacak *idFrom* üyesi **NMHDR** yapısı, söz dizimi ile erişilen `hdr.idFrom`. Bkz: [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr) üyelerinin bir tartışma için **NMHDR** yapısı.  
  
 *lpszText*  
 Bir aracı için metin almak için bir dize adresi.  
  
 *szText*  
 Araç ipucu metnini alır arabelleği. Bir uygulama metni bir dize adresi alternatif olarak bu arabelleğin kopyalayın.  
  
 *hinst*  
 Araç İpucu olarak kullanılacak bir dize içeren örneğinin tutamacını. Varsa *lpszText* adresi araç ipucu metni, bu üye NULL olur.  
  
 Ne zaman işleneceğini `TTN_NEEDTEXT` bildirim iletisi, aşağıdaki yollardan biriyle görüntülenecek dizeyi belirtin:  
  
-   Tarafından belirtilen arabellek için metin kopyalamak *szText* üyesi.  
  
-   Metni içeren arabellek adresini kopyalayın *lpszText* üyesi.  
  
-   Kopyalamak için bir dize kaynağının tanımlayıcısını *lpszText* üye ve kopyalama kaynağı içeren örneğinin tutamacını *hinst* üyesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

