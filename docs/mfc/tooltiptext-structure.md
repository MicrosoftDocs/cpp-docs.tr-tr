---
title: "TOOLTIPTEXT yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TOOLTIPTEXT
dev_langs:
- C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: becbdcfcc6dbd26ae3095de098d12dbc078530cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tooltiptext-structure"></a>TOOLTIPTEXT Yapısı
Yazma işleminde, [araç ipucu bildirim işleyicisi](../mfc/handling-ttn-needtext-notification-for-tool-tips.md), kullanmanız gereken `TOOLTIPTEXT` yapısı. Üyeleri `TOOLTIPTEXT` yapısı şunlardır:  
  
 `typedef struct {`  
  
 `NMHDR     hdr;        // required for all WM_NOTIFY messages`  
  
 `LPTSTR    lpszText;   // see below`  
  
 `TCHAR     szText[80]; // buffer for tool tip text`  
  
 `HINSTANCE hinst;      // see below`  
  
 `UINT      uflags;     // flag indicating how to interpret the`  
  
 `// idFrom member of the NMHDR structure`  
  
 `// that is included in the structure`  
  
 `} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;`  
  
 `hdr`  
 Metin gereken aracı tanımlar. Tek gereksinim duyabileceğiniz bu yapı denetimin komut kimliği üyesidir Denetimin komut kimliği olacak `idFrom` üyesi `NMHDR` sözdizimi ile erişilen yapısı `hdr.idFrom`. Bkz: [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) üyelerinin bir tartışma için `NMHDR` yapısı.  
  
 `lpszText`  
 Bir aracı için metin almak için bir dize adresidir.  
  
 `szText`  
 Araç ipucu metnini alır arabelleği. Bir uygulama metin dizesi adresini belirtme alternatif olarak bu arabelleğin kopyalayın.  
  
 `hinst`  
 Araç İpucu olarak kullanılacak bir dize içeriyor örneği tanıtıcısı. Varsa `lpszText` adresi araç ipucu metnini, bu üye NULL olur.  
  
 Ne zaman işleneceğini `TTN_NEEDTEXT` bildirim iletisi, aşağıdaki yollardan biriyle görüntülenecek dizeyi belirtin:  
  
-   Belirtilen arabellek metin kopyalamak `szText` üyesi.  
  
-   Metni içeren arabelleği adresini kopyalayın `lpszText` üyesi.  
  
-   Bir dize kaynağı tanıtıcısı kopyalama `lpszText` üye ve kopyalama kaynağı içeren örneği tanıtıcısı `hinst` üyesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

