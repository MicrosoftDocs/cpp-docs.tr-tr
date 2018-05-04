---
title: Özyineleme makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2759deaff6014cbba40c97f9d627baf6a800732f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="recursion-macros"></a>Özyineleme Makroları
Özyineleme makroları NMAKE özyinelemeli olarak aramak için kullanın. Özyinelemeli oturumları komut satırı ve ortam değişkeni makroları ve Tools.ini bilgi devralır. Derleme görevleri dosyası tarafından tanımlanan çıkarım kuralları devralmaz veya **. SONEKLERİ** ve **. DEĞERLİ** belirtimleri. Bir özyinelemeli NMAKE oturuma makroları geçirmek için bir ortam değişkeni özyinelemeli çağrısından önce kümesi ile özyinelemeli çağrısı komutta makro tanımlayın veya makro içinde Tools.ini tanımlamak.  
  
|Makrosu|Tanım|  
|-----------|----------------|  
|**YAPMA**|NMAKE çağırmak için özgün olarak kullanılan komutu.<br /><br /> $(MAKE) makrosu nmake.exe için tam yolunu sağlar.|  
|**MAKEDIR**|NMAKE çağrıldığında geçerli dizini.|  
|**MAKEFLAGS**|Seçeneklerinde şu anda etkin. Olarak kullanmak `/$(MAKEFLAGS)`.  Not: /F dahil değildir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel NMAKE Makroları](../build/special-nmake-macros.md)