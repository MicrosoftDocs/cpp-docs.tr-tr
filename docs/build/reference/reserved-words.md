---
title: "Ayrılmış sözcükler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1a7040ac0093471be657c2ed7a064719abcd0230
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|**DIŞARI AKTARMA**|**UYUMSUZ**1|**STACKSIZE**|  
|**SABİT**1|**NONDISCARDABLE**|**SAPLAMA**|  
|**İŞLEVLER**2|**YOK**|**SÜRÜM**|  
|**HEAPSIZE**|**PAYLAŞILMAYAN**|**WINDOWAPI**|  
|**İÇERİ AKTARMALAR**|**NOTWINDOWCOMPAT**1|**WINDOWCOMPAT**|  
|**HANUKA**1|**NESNELERİ**|**WINDOWS**|  
|**DAHİL**2|**ESKİ**1||  
  
 1 Bu terim karşılaştığında bağlayıcı ("göz ardı") bir uyarı gösterir. Ancak, yine ayrılmış bir sözcüktür.  
  
 2 bağlayıcı bu sözcüğü yoksayar ancak hiçbir uyarı yayar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)