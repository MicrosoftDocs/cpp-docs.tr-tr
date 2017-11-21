---
title: "Genel metin eşlemelerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _UNICODE
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
- _UNICODE constant
- TXCHAR type
- generic-text mappings
- _TSCHAR type
- T type
- mappings, generic-text
- _TUCHAR type
- MBCS data type
- _MBCS data type
- _TEXT type
- UNICODE constant
- _T type
ms.assetid: 2848121c-e51f-4b9b-a2e6-833ece4b0cb3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f4067e9555200805631fb72fe3e40afa09c168e3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-generic-text-mappings"></a>Genel Metin Eşlemelerini Kullanma
**Microsoft özel**  
  
 Kod geliştirme için çeşitli uluslararası pazarda basitleştirmek için çok sayıda veri türleri, yordamlar ve diğer nesneleri için Microsoft çalışma zamanı kitaplığı Microsoft'a özgü "genel metin" eşlemeleri sağlar. Bu eşlemeler TCHAR içinde tanımlanmıştır. H. Herhangi bir karakter kümesi üç tür için derlenebilir genel kodlar yazmak için bu ad eşlemeleri kullanabilirsiniz: ASCII (SBCS), MBCS veya Unicode kullanarak tanımladığınız bildirim sabitine bağlı olarak bir `#define` deyimi. Genel metin eşlemeleri ANSI uyumlu olmayan Microsoft uzantıları yer almaktadır.  
  
### <a name="preprocessor-directives-for-generic-text-mappings"></a>Genel metin eşlemeleri önişlemci yönergeleri  
  
|#define|Derlenmiş sürüm|Örnek|  
|--------------|----------------------|-------------|  
|`_UNICODE`|Unicode (geniş karakter)|`_tcsrev`eşler`_wcsrev`|  
|`_MBCS`|Çok baytlı karakter|`_tcsrev`eşler`_mbsrev`|  
|Hiçbiri (varsayılan: ne `_UNICODE` ya da `_MBCS` tanımlanan)|SBCS (ASCII)|`_tcsrev`eşler`strrev`|  
  
 Örneğin, genel metin işlevi `_tcsrev`, TCHAR tanımlı. H eşlendiğini `mbsrev` varsa `MBCS` programınızdaki veya için tanımlanan `_wcsrev` varsa `_UNICODE` tanımlandı. Aksi takdirde `_tcsrev` eşlendiği `strrev`.  
  
 Genel metin veri türü `_TCHAR`, TCHAR ayrıca tanımlı. H eşlemeleri yazmak için `char` varsa `_MBCS` türü için tanımlı `wchar_t` varsa `_UNICODE` tanımlanır ve yazmak için `char` hiçbiri sabiti tanımlanmışsa. Diğer veri türü eşlemeleri TCHAR içinde sağlanır. Programlama kolaylık sağlamak için H ancak `_TCHAR` kullanışlıdır türüdür.  
  
### <a name="generic-text-data-type-mappings"></a>Genel metin veri türü eşlemeleri  
  
|Genel metin veri türü adı|SBCS (_UNICODE, _MBCS tanımlanmamış)|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|----------------------------------|--------------------------------------------|--------------------|-----------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_TINT`|`int`|`int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T`veya`_TEXT`|(Önişlemci tarafından kaldırılır) herhangi bir etkisi|(Önişlemci tarafından kaldırılır) herhangi bir etkisi|`L`(karakter veya dize Unicode karşılığı aşağıdaki dönüştürür)|  
  
 Genel metin eşlemeleri yordamları, değişkenlerin ve diğer nesneleri tam bir listesi için bkz: [genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md).  
  
 Aşağıdaki kod parçası kullanımını göstermek `_TCHAR` ve `_tcsrev` eşleme MBCS, Unicode ve SBCS modelleri için.  
  
```  
_TCHAR *RetVal, *szString;  
RetVal = _tcsrev(szString);  
```  
  
 Varsa `MBCS` bırakıldı tanımlanan önişlemci önceki parça aşağıdaki kodu eşler:  
  
```  
char *RetVal, *szString;  
RetVal = _mbsrev(szString);  
```  
  
 Varsa `_UNICODE` bırakıldı tanımlanan önişlemci aynı parça aşağıdaki kodu eşler:  
  
```  
wchar_t *RetVal, *szString;  
RetVal = _wcsrev(szString);  
```  
  
 Ne `_MBCS` ya da `_UNICODE` bırakıldı tanımlanan önişlemci parça tek baytlı ASCII kod, aşağıdaki gibi eşler:  
  
```  
char *RetVal, *szString;  
RetVal = strrev(szString);  
```  
  
 Bu nedenle yazma, korumanıza ve herhangi bir karakter kümesi üç tür için özel yordamlar çalıştırmak için tek kaynak kodu dosyasının derleyin.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md)   
 [Veri türü eşlemeleri](../c-runtime-library/data-type-mappings.md)   
 [Sabit ve Global değişken eşlemeleri](../c-runtime-library/constant-and-global-variable-mappings.md)   
 [Rutin eşlemeler](../c-runtime-library/routine-mappings.md)   
 [Örnek genel metin programı](../c-runtime-library/a-sample-generic-text-program.md)