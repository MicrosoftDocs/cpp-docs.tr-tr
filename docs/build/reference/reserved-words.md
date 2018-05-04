---
title: Ayrılmış sözcükler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
dev_langs:
- C++
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abe67e1804d436dbd44257f6d7670a71b7f74889
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="reserved-words"></a>Ayrılmış Sözcükler
Aşağıdaki sözcükler bağlayıcı tarafından ayrılmış. Bu adları bağımsız değişken olarak kullanılan [modül tanımlama deyimleri](../../build/reference/module-definition-dot-def-files.md) yalnızca ad çift tırnak işaretleri içine alınırsa ("").  
  
||||  
|-|-|-|  
|**APPLOADER**1|**INİTINSTANCE**2|**ÖNYÜKLEME**|  
|**TEMEL**|**IOPL**|**ÖZEL**|  
|**KOD**|**KİTAPLIK**1|**PROTMODE**2|  
|**UYUMSUZ**|**LOADONCALL**1|**SAF**1|  
|**VERİ**|**LONGNAMES**2|**SALT OKUNUR**|  
|**AÇIKLAMA**|**TAŞINABİLİR**1|**READWRITE**|  
|**DEV386**|**TAŞINABİLİR**1|**REALMODE**1|  
|**DISCARDABLE**|**BİRDEN ÇOK**|**YERLEŞİK**|  
|**DİNAMİK**|**ADI**|**RESIDENTNAME**1|  
|**YALNIZCA YÜRÜTME**|**NEWFILES**2|**BÖLÜMLER**|  
|**EXECUTEONLY**|**NODATA**1|**PARÇALARI**|  
|**EXECUTEREAD**|**NOIOPL**1|**PAYLAŞILAN**|  
|**EXETYPE**|**NONAME**|**TEK**|  
|**EXPORTS**|**UYUMSUZ**1|**STACKSIZE**|  
|**SABİT**1|**NONDISCARDABLE**|**STUB**|  
|**İŞLEVLER**2|**YOK**|**SÜRÜM**|  
|**HEAPSIZE**|**PAYLAŞILMAYAN**|**WINDOWAPI**|  
|**İÇERİ AKTARMALAR**|**NOTWINDOWCOMPAT**1|**WINDOWCOMPAT**|  
|**HANUKA**1|**NESNELERİ**|**WINDOWS**|  
|**DAHİL**2|**ESKİ**1||  
  
 1 Bu terim karşılaştığında bağlayıcı ("göz ardı") bir uyarı gösterir. Ancak, yine ayrılmış bir sözcüktür.  
  
 2 bağlayıcı bu sözcüğü yoksayar ancak hiçbir uyarı yayar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)