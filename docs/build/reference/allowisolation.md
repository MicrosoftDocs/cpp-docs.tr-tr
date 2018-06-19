---
title: -ALLOWISOLATION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ALLOWISOLATION
dev_langs:
- C++
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5cb92a7f31d48dad4a7fb608703c71ccc661e176
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368980"
---
# <a name="allowisolation"></a>/ALLOWISOLATION
Bildirim arama davranışını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
/ALLOWISOLATION[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/ ALLOWISOLATION** işletim sisteminin aramaları ve yükleri bildirim neden olur.  
  
 **/ ALLOWISOLATION** varsayılandır.  
  
 **/ALLOWISOLATION:No** gibi varsa hiçbir bildirimi ve nedenleri yürütülebilir dosyalar yüklenir gösterir [EDITBIN başvurusu](../../build/reference/editbin-reference.md) ayarlamak için `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` isteğe bağlı başlığının içinde bit `DllCharacteristics` alan.  
  
 Yalıtım için yürütülebilir bir dosya devre dışı bırakıldığında, Windows Yükleyici yeni oluşturulan işlemi için bir uygulama bildirimi Bul dener. Yeni işlem yürütülebilir bildiriminde yok ya da adına sahip bir bildirim ise olsa bile varsayılan etkinleştirme bağlamı yok *yürütülebilir dosya adı*. exe.manifest.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EDITBIN seçenekleri](../../build/reference/editbin-options.md)   
 [/ ALLOWISOLATION (bildirim arama)](../../build/reference/allowisolation-manifest-lookup.md)   
 [Dosyaları başvuru bildirimi](http://msdn.microsoft.com/library/aa375632.aspx)