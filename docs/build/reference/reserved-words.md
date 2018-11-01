---
title: Ayrılmış sözcükler
ms.date: 11/04/2016
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
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
ms.openlocfilehash: 360baf479f9100483fe694ca8860dfc1d7ebfe11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502472"
---
# <a name="reserved-words"></a>Ayrılmış sözcükler

Bağlayıcı tarafından aşağıdaki sözcükler ayrılmıştır. Bu adlar, bağımsız değişkenleri olarak kullanılabilir [modül tanımlama deyimleri](../../build/reference/module-definition-dot-def-files.md) yalnızca adı çift tırnak işaretleri arasına alınmışsa ("").

||||
|-|-|-|
|**APPLOADER**<sup>1</sup>|**INİTINSTANCE**<sup>2</sup>|**PRELOAD**|
|**TEMEL**|**IOPL**|**ÖZEL**|
|**KOD**|**KİTAPLIK**<sup>1</sup>|**PROTMODE**<sup>2</sup>|
|**UYGUN**|**LOADONCALL**<sup>1</sup>|**SAF**<sup>1</sup>|
|**VERİ**|**LONGNAMES**<sup>2</sup>|**SALT OKUNUR**|
|**AÇIKLAMASI**|**TAŞINABİLİR**<sup>1</sup>|**READWRITE**|
|**DEV386**|**TAŞINABİLİR**<sup>1</sup>|**REALMODE**<sup>1</sup>|
|**DISCARDABLE**|**BİRDEN ÇOK**|**YERLEŞİK**|
|**DİNAMİK**|**ADI**|**RESIDENTNAME**<sup>1</sup>|
|**YALNIZCA YÜRÜTME**|**NEWFILES**<sup>2</sup>|**BÖLÜMLERİ**|
|**EXECUTEONLY**|**NODATA**<sup>1</sup>|**PARÇALARI**|
|**EXECUTEREAD**|**NOIOPL**<sup>1</sup>|**PAYLAŞILAN**|
|**EXETYPE**|**NONAME**|**TEK**|
|**EXPORTS**|**UYUMSUZ**<sup>1</sup>|**STACKSIZE**|
|**SABİT**<sup>1</sup>|**NONDISCARDABLE**|**STUB**|
|**İŞLEVLERİ**<sup>2</sup>|**YOK**|**SÜRÜM**|
|**HEAPSIZE**|**PAYLAŞILMAYAN**|**WINDOWAPI**|
|**İÇERİ AKTARMALAR**|**NOTWINDOWCOMPAT**<sup>1</sup>|**WINDOWCOMPAT**|
|**HANUKA**<sup>1</sup>|**NESNELERİ**|**WINDOWS**|
|**DAHİL**<sup>2</sup>|**ESKİ**<sup>1</sup>||

<sup>1</sup> bu terim karşılaştığında bağlayıcı ("yoksayıldı") bir uyarı verir. Ancak, yine de ayrılmış bir sözcüktür.

<sup>2</sup> bağlayıcı Bu word gözardı eder, ancak hiçbir uyarı verir.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)
- [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)