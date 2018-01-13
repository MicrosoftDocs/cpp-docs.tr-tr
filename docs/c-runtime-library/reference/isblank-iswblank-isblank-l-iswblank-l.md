---
title: "EBOŞSA, iswblank, _isblank_l, _iswblank_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- isblank
- _isblank_l
- iswblank
- _iswblank_l
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
- _iswblank_l
- isblank
- _istblank_l
- _istblank
- _isblank_l
- iswblank
dev_langs: C++
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5185820e3b8bcb2b5fab1adfaee247743f2e464f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="isblank-iswblank-isblankl-iswblankl"></a>isblank, iswblank, _isblank_l, _iswblank_l
Tamsayı boşluk karakteri temsil edip etmediğini belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int isblank(  
   int c   
);  
int iswblank(  
   wint_t c   
);  
int _isblank_l(  
   int c,  
   _locale_t locale  
);  
int _iswblank_l(  
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
 Bu yordamları döndürür sıfır olmayan IF her `c` belirli bir boşluk veya yatay sekme karakteri gösterimidir ya da yerel ayarlara özgü bir metin satırının içinde sözcükleri ayırmak için kullanılan karakter kümesi biridir. `isblank`sıfır olmayan bir değer döndürür `c` bir boşluk karakteri olduğunda (0x20) veya yatay sekme karakterini (0x09). İçin test koşul sonucunu `isblank` işlevleri bağımlı `LC_CTYPE` kategori ayar yerel; daha fazla bilgi için bkz. [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Bu işlevlerin olmayan sürümleri `_l` tüm yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; olan sürümleri `_l` soneki, bunun yerine geçirilen yerel kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 `iswblank`sıfır olmayan bir değer döndürür `c` standart bir alana karşılık gelen bir geniş karakter ya da yatay sekme karakteri.  
  
 Davranışını `isblank` ve `_isblank_l` tanımsız ise `c` EOF değil veya 0'dan 0xFF (bunlar dahil) aralığında. CRT hata ayıklama Kitaplığı kullanıldığında ve `c` işlevleri olursa bu değerleri onayı ifade değil.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istblank`|`isblank`|[_ismbcblank](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswblank`|  
|`_istblank_l`|`_isblank_l`|[_ismbcblank_l](../../c-runtime-library/reference/ismbcgraph-functions.md)|`_iswblank_l`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`isblank`|\<CType.h >|  
|`iswblank`|\<CType.h > veya \<wchar.h >|  
|`_isblank_l`|\<CType.h >|  
|`_iswblank_l`|\<CType.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karakter Sınıflaması](../../c-runtime-library/character-classification.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)