---
title: -ALLOWISOLATION | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ALLOWISOLATION
dev_langs:
- C++
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ba0295d73e51e28fbdd953d7d9a3a2ae5131c27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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