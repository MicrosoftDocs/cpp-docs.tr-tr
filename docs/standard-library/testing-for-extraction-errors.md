---
title: "Ayıklama hataları için test yapma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 232dbd4312bbb8a0f16b6095622680f070ff2905
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="testing-for-extraction-errors"></a>Ayıklama Hataları İçin Test Yapma
Çıktı ele hata işleme işlevleri [hata işleme işlevleri](../standard-library/output-file-stream-member-functions.md), akış girişi için geçerlidir. Hata ayıklama sırasında test önemlidir. Bu bildirimi göz önünde bulundurun:  
  
```  
cin>> n;  
```  
  
 Varsa `n` 32.767 büyük bir değer imzalı bir tamsayı (izin verilen en fazla değer veya MAX_INT) akışın ayarlar `fail` bit ve `cin` nesne kullanılamaz olur. Tüm sonraki ayıklamaları sonuçla anlık bir return içinde depolanan herhangi bir değer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Giriş Akışları](../standard-library/input-streams.md)

