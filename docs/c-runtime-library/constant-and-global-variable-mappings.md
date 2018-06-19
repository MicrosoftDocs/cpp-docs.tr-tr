---
title: Sabit ve Global değişken eşlemeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _tenviron
- _TEOF
- _tfinddata_t
dev_langs:
- C++
helpviewer_keywords:
- tfinddatat function
- tenviron function
- TEOF type
- _TEOF type
- generic-text mappings
- _tenviron function
- _tfinddata_t function
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96c30f939670931ab031349bc5e9ddcce54e1891
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387531"
---
# <a name="constant-and-global-variable-mappings"></a>Sabit ve Global Değişken Eşlemeleri
Bu genel metin sabiti, genel değişkeni ve standart türü eşlemeleri TCHAR içinde tanımlanır. H ve olup olmadığına göre değişir sabiti `_UNICODE` veya `_MBCS` programınıza tanımlandı.  
  
### <a name="generic-text-constant-and-global-variable-mappings"></a>Genel metin sabit ve Global değişken eşlemeleri  
  
|Genel metin - nesne adı|SBCS (_UNICODE, _MBCS tanımlanmamış)|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|----------------------------------|--------------------------------------------|--------------------|-----------------------|  
|`_TEOF`|`EOF`|`EOF`|`WEOF`|  
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md)   
 [Veri türü eşlemeleri](../c-runtime-library/data-type-mappings.md)   
 [Rutin eşlemeler](../c-runtime-library/routine-mappings.md)   
 [Örnek genel metin programı](../c-runtime-library/a-sample-generic-text-program.md)   
 [Genel Metin Eşlemelerini Kullanma](../c-runtime-library/using-generic-text-mappings.md)