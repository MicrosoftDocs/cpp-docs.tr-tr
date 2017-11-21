---
title: "Özyineleme makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 41354c34fb21da7f568718489495991cbd1bae43
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="recursion-macros"></a>Özyineleme Makroları
Özyineleme makroları NMAKE özyinelemeli olarak aramak için kullanın. Özyinelemeli oturumları komut satırı ve ortam değişkeni makroları ve Tools.ini bilgi devralır. Derleme görevleri dosyası tarafından tanımlanan çıkarım kuralları devralmaz veya **. SONEKLERİ** ve **. DEĞERLİ** belirtimleri. Bir özyinelemeli NMAKE oturuma makroları geçirmek için bir ortam değişkeni özyinelemeli çağrısından önce kümesi ile özyinelemeli çağrısı komutta makro tanımlayın veya makro içinde Tools.ini tanımlamak.  
  
|Makrosu|Tanım|  
|-----------|----------------|  
|**YAPMA**|NMAKE çağırmak için özgün olarak kullanılan komutu.<br /><br /> $(MAKE) makrosu nmake.exe için tam yolunu sağlar.|  
|**MAKEDIR**|NMAKE çağrıldığında geçerli dizini.|  
|**MAKEFLAGS**|Seçeneklerinde şu anda etkin. Olarak kullanmak `/$(MAKEFLAGS)`.  Not: /F dahil değildir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel NMAKE makroları](../build/special-nmake-macros.md)