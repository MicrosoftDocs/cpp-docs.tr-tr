---
title: NMAKE çıkış kodları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e71442e1e36dbd69afa65051cbf08f403bf8b31
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [NMAKE Çalıştırma](../build/running-nmake.md)