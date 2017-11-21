---
title: "Ayıklama hataları için test yapma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 088cc150513d593aff5d4250c899eb3712c5fe39
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="testing-for-extraction-errors"></a>Ayıklama Hataları İçin Test Yapma
Çıktı ele hata işleme işlevleri [hata işleme işlevleri](../standard-library/output-file-stream-member-functions.md), akış girişi için geçerlidir. Hata ayıklama sırasında test önemlidir. Bu bildirimi göz önünde bulundurun:  
  
```  
cin>> n;  
```  
  
 Varsa `n` 32.767 büyük bir değer imzalı bir tamsayı (izin verilen en fazla değer veya MAX_INT) akışın ayarlar `fail` bit ve `cin` nesne kullanılamaz olur. Tüm sonraki ayıklamaları sonuçla anlık bir return içinde depolanan herhangi bir değer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Giriş akışları](../standard-library/input-streams.md)

