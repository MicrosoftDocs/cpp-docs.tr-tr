---
title: 'Nasıl yapılır: ileti eşleme çapraz başvurusunu kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d59d0bfc75f654cd9f8f15ff851ad42a619e271f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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

