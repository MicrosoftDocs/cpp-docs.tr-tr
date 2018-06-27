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
ms.openlocfilehash: 8cae7efbee59b24ff34518b62ff212d436973053
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953938"
---
# <a name="tooltiptext-structure"></a>TOOLTIPTEXT Yapısı
Yazma işleminde, [araç ipucu bildirim işleyicisi](../mfc/handling-ttn-needtext-notification-for-tool-tips.md), kullanmanız gereken **TOOLTIPTEXT** yapısı. Üyeleri **TOOLTIPTEXT** yapısı şunlardır:  
  
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
 Metin gereken aracı tanımlar. Tek gereksinim duyabileceğiniz bu yapı denetimin komut kimliği üyesidir Denetimin komut kimliği olacak *idFrom* üyesi **NMHDR** sözdizimi ile erişilen yapısı `hdr.idFrom`. Bkz: [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) üyelerinin bir tartışma için **NMHDR** yapısı.  
  
 *lpszText*  
 Bir aracı için metin almak için bir dize adresidir.  
  
 *szText*  
 Araç ipucu metnini alır arabelleği. Bir uygulama metin dizesi adresini belirtme alternatif olarak bu arabelleğin kopyalayın.  
  
 *hinst*  
 Araç İpucu olarak kullanılacak bir dize içeriyor örneği tanıtıcısı. Varsa *lpszText* adresi araç ipucu metnini, bu üye NULL olur.  
  
 Ne zaman işleneceğini `TTN_NEEDTEXT` bildirim iletisi, aşağıdaki yollardan biriyle görüntülenecek dizeyi belirtin:  
  
-   Belirtilen arabellek metin kopyalamak *szText* üyesi.  
  
-   Metni içeren arabelleği adresini kopyalayın *lpszText* üyesi.  
  
-   Bir dize kaynağı tanıtıcısı kopyalama *lpszText* üye ve kopyalama kaynağı içeren örneği tanıtıcısı *hinst* üyesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

