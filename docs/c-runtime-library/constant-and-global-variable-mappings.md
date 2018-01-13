---
title: "Sabit ve Global değişken eşlemeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _tenviron
- _TEOF
- _tfinddata_t
dev_langs: C++
helpviewer_keywords:
- tfinddatat function
- tenviron function
- TEOF type
- _TEOF type
- generic-text mappings
- _tenviron function
- _tfinddata_t function
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb767bb3dbfbde8d73ab81acc444a772a05e7880
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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