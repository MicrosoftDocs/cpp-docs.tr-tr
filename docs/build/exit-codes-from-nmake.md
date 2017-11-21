---
title: "NMAKE çıkış kodları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bb5548d74544ba4277fa1d901ffa9f0b91b83f2e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="exit-codes-from-nmake"></a>NMAKE Çıkış Kodları
NMAKE aşağıdaki çıkış kodlarını döndürür:  
  
|Kod|Açıklama|  
|----------|-------------|  
|0|Herhangi bir hata (büyük olasılıkla bir uyarı)|  
|1.|(Yalnızca/k kullanıldığında verilen) tamamlanmamış derleme|  
|2|Program hata, nedeni şunlardan biri:|  
||-Derleme görevleri dosyası bir sözdizimi hatası|  
||-Bir hata veya çıkış kodu komutundan|  
||-Kullanıcı tarafından kesintiyi|  
|4|Sistem hatası: bellek yetersiz|  
|255|Hedef (yalnızca /Q kullanıldığında verilen) güncel değil|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE çalıştırma](../build/running-nmake.md)