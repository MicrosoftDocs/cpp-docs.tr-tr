---
title: "Ayrılmış sözcükler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
dev_langs:
- C++
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 35f9a3e907b72b4b8cf8e673e771832ba3fc0527
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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