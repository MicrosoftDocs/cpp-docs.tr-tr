---
title: HTTP temelleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTTP [MFC], return codes
- return codes [MFC]
- HTTP requests [MFC], return codes
ms.assetid: 5b7421bf-42c8-4f3a-8566-8ff5957f58cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56a2692edd9d41f80023e44f4ca8172cba8f9d00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
  
 [http://www.w3.org/pub/WWW/Protocols/](http://www.w3.org/pub/www/protocols/)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)

