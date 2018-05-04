---
title: Dosya adı makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e49c65a642dcee3e0f04fb5000a390fccae98ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="filename-macros"></a>Dosya Adı Makroları
Dosya adı makroları (disk üzerinde değil tam dosya adı belirtimleri) bağımlılık belirtilen dosya adları olarak önceden tanımlanmıştır. Bu makroları çağrıldığında parantez içine alınmış gerekmez; yalnızca bir $ gösterildiği gibi belirtin.  
  
|Makrosu|Açıklama|  
|-----------|-------------|  
|**$@**|Şu anda belirtilen geçerli hedefin tam adı (yol, bir taban adına, uzantısı).|  
|**$$@**|Şu anda belirtilen geçerli hedefin tam adı (yol, bir taban adına, uzantısı). Yalnızca bir bağımlılık olarak bağlı olarak geçerli.|  
|**$\***|Geçerli hedefin yol ve temel adı eksi dosya uzantısı.|  
|**$\*\***|Tüm bağımlılıklar geçerli hedef.|  
|**$?**|Tüm bağımlıları olan geçerli hedefi daha sonraki bir zaman damgasına sahip.|  
|**$<**|Bağımlı dosya olan geçerli hedefi daha sonraki bir zaman damgasına sahip. Yalnızca çıkarım kuralları komutlarda geçerli.|  
  
 Önceden tanımlanmış filename makrosu parçası belirtmek için bir makrosu değiştirici ekleme ve değiştirilmiş makrosu parantez içine alın.  
  
|Değiştirici|Sonuçta elde edilen dosya adı bölümü|  
|--------------|-----------------------------|  
|**D**|Sürücü artı dizini|  
|**B**|Temel adı|  
|**F**|Taban adına ve uzantısı|  
|**R**|Sürücü artı dizin artı temel adı|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel NMAKE Makroları](../build/special-nmake-macros.md)