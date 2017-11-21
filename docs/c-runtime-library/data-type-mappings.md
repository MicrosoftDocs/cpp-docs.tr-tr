---
title: "Veri türü eşlemeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _TXCHAR
- _TUCHAR
- _TINT
- _TSCHAR
- _TCHAR
- TCHAR::H
- TCHAR
- _T
- _TEXT
dev_langs: C++
helpviewer_keywords:
- _TXCHAR type
- TINT type
- _TCHAR type
- TSCHAR type
- TEXT type
- TCHAR type
- TCHAR.H data types, mappings defined in
- generic-text data types
- _TINT type
- TUCHAR type
- TXCHAR type
- _TSCHAR type
- T type
- _TUCHAR type
- _TEXT type
- _T type
ms.assetid: 4e573c05-8800-468b-ae5f-76ff7409835e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 217290399a03174e599117077b27116a86808f7f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="data-type-mappings"></a>Veri Türü Eşlemeleri
Bu veri türü eşlemeleri TCHAR içinde tanımlanmıştır. H ve olup olmadığına göre değişir sabiti `_UNICODE` veya `_MBCS` programınıza tanımlandı.  
  
 İlgili bilgi için bkz: [kullanarak TCHAR. _MBCS Kodu ile H veri türleri](../text/using-tchar-h-data-types-with-mbcs-code.md).  
  
### <a name="generic-text-data-type-mappings"></a>Genel metin veri türü eşlemeleri  
  
|Genel metin<br /><br /> veri türü adı|SBCS (_UNICODE,<br /><br /> _MBCS değil<br /><br /> tanımlanan)|_MBCS<br /><br /> tanımlanmış|_UNICODE<br /><br /> tanımlanmış|  
|--------------------------------------|----------------------------------------------------|------------------------|---------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_tfinddata_t`|`_finddata_t`|`_finddata_t`|`_wfinddata_t`|  
|`_tfinddata64_t`|`__finddata64_t`|`__finddata64_t`|`__wfinddata64_t`|  
|`_tfinddatai64_t`|`_finddatai64_t`|`_finddatai64_t`|`_wfinddatai64_t`|  
|`_TINT`|`int`|`int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T`veya`_TEXT`|(Önişlemci tarafından kaldırılır) herhangi bir etkisi|(Önişlemci tarafından kaldırılır) herhangi bir etkisi|`L`(karakter veya dize Unicode karşılığı aşağıdaki dönüştürür)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md)   
 [Sabit ve Global değişken eşlemeleri](../c-runtime-library/constant-and-global-variable-mappings.md)   
 [Rutin eşlemeler](../c-runtime-library/routine-mappings.md)   
 [Örnek genel metin programı](../c-runtime-library/a-sample-generic-text-program.md)   
 [Genel metin eşlemelerini kullanma](../c-runtime-library/using-generic-text-mappings.md)