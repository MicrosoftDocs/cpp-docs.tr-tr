---
title: "Nasıl yapılır: ileti eşleme çapraz başvurusunu kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.messages
dev_langs: C++
helpviewer_keywords: windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ffa7b39962d78476e971750e92569eb14229606b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-the-message-map-cross-reference"></a>Nasıl yapılır: İleti Eşleme Çapraz Başvurusunu Kullanma
Etiketli girdileri \<memberFxn >, kendi üye işlevi türetilmiş için yazma [CWnd](../../mfc/reference/cwnd-class.md) sınıfı. İşlevinizi istediğiniz herhangi bir ad verin. Gibi diğer işlevleri `OnActivate`, sınıfının üye işlevleri `CWnd`. Çağırdıysanız, iletiyi geçirirler `DefWindowProc` Windows işlevi. Windows bildirim iletilerini işlemek için karşılık gelen geçersiz kılma `CWnd` türetilmiş sınıfınızda işlevi. İşlevinizi temel sınıfı izin vermek için taban sınıf içinde geçersiz kılınan işlevi çağırmalıdır ve Windows iletisine yanıt.  
  
 Her durumda, işlev prototipi koyun `CWnd`-türetilmiş sınıf üstbilgi ve kod gösterildiği gibi ileti eşleme girişi.  
  
 Aşağıdaki terimler kullanılır:  
  
|Terim|Tanım|  
|----------|----------------|  
|kimlik|Herhangi bir kullanıcı tarafından tanımlanan menü öğesi kimliği (**WM_COMMAND** iletileri) veya Kimliğine (alt pencere bildirim iletilerini) denetim.|  
|"iletisi" ve "wNotifyCode"|Windows, WINDOWS tanımlanan kimlikleri iletisi. H.|  
|nMessageVariable|Dönüş değerini içeren bir değişkeni adını **RegisterWindowMessage** Windows işlevi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İleti eşlemeleri](../../mfc/reference/message-maps-mfc.md)

