---
title: HTTP temelleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- HTTP [MFC], return codes
- return codes [MFC]
- HTTP requests [MFC], return codes
ms.assetid: 5b7421bf-42c8-4f3a-8566-8ff5957f58cc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 67921e0667267b99b3787d55fa7ff564aa543ae7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="http-basics"></a>HTTP Temelleri
Internet uygulamasını yazarken, genellikle inceleyin ve HTTP üstbilgisinde yer alan bilgiler ekleyin. Dönüş kodları, başarı veya başarısızlık istenen olay gösterir. Birçok ortak dönüş kodları aşağıdaki tabloda listelenmiştir.  
  
|Dönüş kodu|Açıklama|  
|-----------------|-------------|  
|200|URL, bulunan iletim izler|  
|400|Anlamsız isteği|  
|404|İstenen URL bulunamadı|  
|405|Sunucu istenen yöntemi desteklemiyor|  
|500|Bilinmeyen sunucu hatası|  
|503|Hizmet kullanılamıyor|  
  
 HTTP yanıtını aşağıdaki tabloda gösterildiği gibi gruplandırılır.  
  
|Grup|Açıklama|  
|-----------|-------------|  
|200-299|Başarılı|  
|300-399|Bilgiler|  
|400-499|İstek hatası|  
|500-599|Sunucu hatası|  
  
 Köprü Metni Aktarım Protokolü (HTTP) bir iletilir bilgi systems uygulama düzeyi protokolüdür. Köprü Metni Aktarım Protokolü (HTTP) belirtimi HTTP ve Web tarayıcıları ve sunucuları nasıl iletişim kuracağını hakkında daha fazla bilgi için bkz:  
  
 [http://www.w3.org/pub/www/Protocols/](http://www.w3.org/pub/www/protocols/)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)

