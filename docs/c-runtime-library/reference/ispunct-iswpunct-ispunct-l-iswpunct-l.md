---
title: ispunct, iswpunct, _ispunct_l, _iswpunct_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- ispunct
- _iswpunct_l
- iswpunct
- _ispunct_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- iswpunct
- _istpunct
- ispunct
dev_langs:
- C++
helpviewer_keywords:
- _istpunct function
- _ispunct_l function
- iswpunct function
- ispunct function
- istpunct function
- ispunct_l function
- _iswpunct_l function
- iswpunct_l function
ms.assetid: 94403240-85c8-40a4-9c2b-e3e95c729c76
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc86de73132dcefc57602586b679b95333c99c2e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ispunct-iswpunct-ispunctl-iswpunctl"></a>ispunct, iswpunct, _ispunct_l, _iswpunct_l
Tamsayı bir noktalama karakteri temsil edip etmediğini belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int ispunct(  
   int c   
);  
int iswpunct(  
   wint_t c   
);  
int _ispunct_l(  
   int c,  
   _locale_t locale  
);  
int _iswpunct_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Test etmek için bir tamsayı.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yordamları döndürür sıfır olmayan IF her `c` bir noktalama karakteri belirli bir gösterimidir. `ispunct` bir boşluk karakteri veya kendisi için bir karakter değil herhangi bir yazdırılabilir karakter için sıfır olmayan bir değer döndürür `isalnum` sıfır olmayan bir değer değil. `iswpunct` alan geniş karakter ne olduğu için geniş karakter olan herhangi bir yazdırılabilir geniş karakter için sıfır olmayan bir değer döndürür `iswalnum` sıfır olmayan bir değer değil. Bu yordamlar her 0 döndürür `c` test durumu uygun değil.  
  
 İçin test koşul sonucunu `ispunct` işlevi bağımlı `LC_CTYPE` yerel kategori ayarı; bkz: [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin olmayan sürümleri `_l` tüm yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; olan sürümleri `_l` soneki, bunun yerine geçirilen yerel kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Davranışını `ispunct` ve `_ispunct_l` tanımsız ise `c` EOF değil veya 0'dan 0xFF (bunlar dahil) aralığında. CRT hata ayıklama Kitaplığı kullanıldığında ve `c` işlevleri olursa bu değerleri onayı ifade değil.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|**_** `istpunct`|`ispunct`|[_ismbcpunct](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswpunct`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`ispunct`|\<ctype.h>|  
|`iswpunct`|\<CType.h > veya \<wchar.h >|  
|`_ispunct_l`|\<ctype.h>|  
|`_iswpunct_l`|\<CType.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karakter Sınıflaması](../../c-runtime-library/character-classification.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)