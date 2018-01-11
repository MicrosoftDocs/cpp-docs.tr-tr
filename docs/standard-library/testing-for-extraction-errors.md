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
ms.workload: cplusplus
ms.openlocfilehash: 0dc8c053181eda8535eb101352e9aa50053a28f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="testing-for-extraction-errors"></a>Ayıklama Hataları İçin Test Yapma
Çıktı ele hata işleme işlevleri [hata işleme işlevleri](../standard-library/output-file-stream-member-functions.md), akış girişi için geçerlidir. Hata ayıklama sırasında test önemlidir. Bu bildirimi göz önünde bulundurun:  
  
```  
cin>> n;  
```  
  
 Varsa `n` 32.767 büyük bir değer imzalı bir tamsayı (izin verilen en fazla değer veya MAX_INT) akışın ayarlar `fail` bit ve `cin` nesne kullanılamaz olur. Tüm sonraki ayıklamaları sonuçla anlık bir return içinde depolanan herhangi bir değer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Giriş Akışları](../standard-library/input-streams.md)

