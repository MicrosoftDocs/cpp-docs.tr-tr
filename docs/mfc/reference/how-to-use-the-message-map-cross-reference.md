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
ms.openlocfilehash: bf76d8f7bb86bf3325a072df80a45e2f0a3ad985
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338904"
---
# <a name="how-to-use-the-message-map-cross-reference"></a>Nasıl yapılır: İleti Eşleme Çapraz Başvurusunu Kullanma
Etiketli girdileri \<memberFxn >, kendi üye işlevi için türetilmiş yazma [CWnd](../../mfc/reference/cwnd-class.md) sınıfı. İşlevinizi istediğiniz herhangi bir ad verin. Gibi diğer işlevleri `OnActivate`, sınıfın üye işlevleri `CWnd`. Çağrılırsa, bunlar iletiye geçirmek `DefWindowProc` Windows işlevi. Windows bildirim iletilerini işlemek için karşılık gelen geçersiz kılma `CWnd` türetilmiş sınıfınızın bir işlevde. İşlevinizi geçersiz kılınmış işlev temel sınıf izin vermek için temel sınıfta çağırmalıdır ve Windows iletiye yanıt vermek.  
  
 Her durumda, işlev prototipi koymak `CWnd`-türetilmiş sınıf üstbilgi ve kod gösterildiği ileti eşleme girişi.  
  
 Aşağıdaki terimler kullanılır:  
  
|Terim|Tanım|  
|----------|----------------|  
|kimlik|Tüm kullanıcı tanımlı bir menü öğesi kimliği (WM_COMMAND iletileri) veya denetim kimliği (alt pencere bildirim iletisi).|  
|"ileti" ve "wNotifyCode"|Windows, WİNDOWS'da tanımlandığı gibi kimlikleri ileti. H|  
|nMessageVariable|Dönüş değeri içeren değişkenin adını `RegisterWindowMessage` Windows işlevi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İleti eşlemeleri](../../mfc/reference/message-maps-mfc.md)

