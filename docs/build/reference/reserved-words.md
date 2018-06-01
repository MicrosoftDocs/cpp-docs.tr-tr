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
ms.openlocfilehash: 132bd8e5ba66cbf9486a6da4747994c667e2f6e7
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705666"
---
# <a name="reserved-words"></a>Ayrılmış sözcükler

Aşağıdaki sözcükler bağlayıcı tarafından ayrılmış. Bu adları bağımsız değişken olarak kullanılan [modül tanımlama deyimleri](../../build/reference/module-definition-dot-def-files.md) yalnızca ad çift tırnak işaretleri içine alınırsa ("").

||||
|-|-|-|
|**APPLOADER**<sup>1</sup>|**INİTINSTANCE**<sup>2</sup>|**ÖNYÜKLEME**|
|**TEMEL**|**IOPL**|**ÖZEL**|
|**KOD**|**KİTAPLIK**<sup>1</sup>|**PROTMODE**<sup>2</sup>|
|**UYUMSUZ**|**LOADONCALL**<sup>1</sup>|**SAF**<sup>1</sup>|
|**VERİ**|**LONGNAMES**<sup>2</sup>|**SALT OKUNUR**|
|**AÇIKLAMA**|**TAŞINABİLİR**<sup>1</sup>|**READWRITE**|
|**DEV386**|**TAŞINABİLİR**<sup>1</sup>|**REALMODE**<sup>1</sup>|
|**DISCARDABLE**|**BİRDEN ÇOK**|**YERLEŞİK**|
|**DİNAMİK**|**ADI**|**RESIDENTNAME**<sup>1</sup>|
|**YALNIZCA YÜRÜTME**|**NEWFILES**<sup>2</sup>|**BÖLÜMLER**|
|**EXECUTEONLY**|**NODATA**<sup>1</sup>|**PARÇALARI**|
|**EXECUTEREAD**|**NOIOPL**<sup>1</sup>|**PAYLAŞILAN**|
|**EXETYPE**|**NONAME**|**TEK**|
|**EXPORTS**|**UYUMSUZ**<sup>1</sup>|**STACKSIZE**|
|**SABİT**<sup>1</sup>|**NONDISCARDABLE**|**STUB**|
|**İŞLEVLER**<sup>2</sup>|**YOK**|**SÜRÜM**|
|**HEAPSIZE**|**PAYLAŞILMAYAN**|**WINDOWAPI**|
|**İÇERİ AKTARMALAR**|**NOTWINDOWCOMPAT**<sup>1</sup>|**WINDOWCOMPAT**|
|**HANUKA**<sup>1</sup>|**NESNELERİ**|**WINDOWS**|
|**DAHİL**<sup>2</sup>|**ESKİ**<sup>1</sup>||

<sup>1</sup> bu terim karşılaştığında bağlayıcı ("göz ardı") bir uyarı gösterir. Ancak, yine ayrılmış bir sözcüktür.

<sup>2</sup> bağlayıcı bu sözcüğü yoksayar ancak hiçbir uyarı yayar.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)
- [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)