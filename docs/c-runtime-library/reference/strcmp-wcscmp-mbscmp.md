---
title: strcmp, wcscmp, _mbscmp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- wcscmp
- _mbscmp
- strcmp
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _mbscmp
- wcscmp
- strcmp
- _tcscmp
- _ftcscmp
dev_langs:
- C++
helpviewer_keywords:
- tcscmp function
- strcmp function
- strings [C++], comparing
- mbscmp function
- string comparison [C++]
- _mbscmp function
- wcscmp function
- _tcscmp function
- _ftcscmp function
- ftcscmp function
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
caps.latest.revision: ''
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: addc2c215d0c914e3caee3dba4d32f94ca91e62c
ms.sourcegitcommit: 604907f77eb6c5b1899194a9877726f3e8c2dabc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="strcmp-wcscmp-mbscmp"></a>strcmp, wcscmp, _mbscmp
Dizeleri karşılaştırın.  
  
> [!IMPORTANT]
>  `_mbscmp`, Windows Çalışma Zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int strcmp(  
   const char *string1,  
   const char *string2   
);  
int wcscmp(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbscmp(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `string1`, `string2`  
 Karşılaştırılacak null ile sonlandırılmış dizeler.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her biri için dönüş değeri sıralı ilişkisi gösterir `string1` için `string2`.  
  
|Değer|Dize2 Dize1 ilişkisi|  
|-----------|----------------------------------------|  
|< 0|`string1` Olan küçüktür `string2`|  
|0|`string1` aynıdır `string2`|  
|> 0|`string1` Değerinden büyük `string2`|  
  
 Parametre doğrulama hata `_mbscmp` döndürür `_NLSCMPERROR`, içinde tanımlanan \<string.h > ve \<mbstring.h >.  
  
## <a name="remarks"></a>Açıklamalar  
 `strcmp` İşlevi gerçekleştiren bir sıra karşılaştırması `string1` ve `string2` ve ilişkilerini gösteren bir değer döndürür. `wcscmp` ve `_mbscmp` , sırasıyla, joker karakter ve çok baytlı karakter sürümleridir `strcmp`. `_mbscmp` çok baytlı karakter sıralarının geçerli birden çok baytlı kod sayfasına göre tanır ve döndürür `_NLSCMPERROR` bir hata. Daha fazla bilgi için bkz: [kod sayfaları](../../c-runtime-library/code-pages.md). Ayrıca, varsa `string1` veya `string2` null işaretçi `_mbscmp` açıklandığı gibi geçersiz bir parametre işleyiciyi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `_mbscmp` döndürür `_NLSCMPERROR` ve ayarlar `errno` için `EINVAL`. `strcmp` ve `wcscmp` parametrelerini doğrulamaz. Bu üç işlevler aynı şekilde aksi davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcscmp`|`strcmp`|`_mbscmp`|`wcscmp`|  
  
 `strcmp` İşlevler farklı `strcoll` , işlevlerde `strcmp` karşılaştırmaları sıralı ve yerel ayar tarafından etkilenmez. `strcoll` kullanarak dizeleri lexicographically karşılaştırır `LC_COLLATE` geçerli yerel ayar kategorisi. Hakkında daha fazla bilgi için `LC_COLLATE` kategorisi, bkz: [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 "C" yerel karakter kümesi (ASCII karakter kümesi) karakter sırasını lexicographic karakter sırası ile aynıdır. Ancak, diğer yerlerde karakter kümesinden karakter sırasını lexicographic siparişte farklı olabilir. Örneğin, Avrupa belirli yerlerde karakter 'a' (değer 0x61) karakterinin önünde 'ä' (değer 0xE4) karakter kümesi, ancak 'ä' gelen önünde karakter karakter gelir 'bir' lexicographically.  
  
 Karakter kümesi ve lexicographic karakter sırası için farklı yerlerde kullandığınız `strcoll` yerine `strcmp` dizeleri lexicographic karşılaştırması. Alternatif olarak, kullanabileceğiniz `strxfrm` özgün dizeleri ve sonra kullanıma `strcmp` elde edilen dizelerde.  
  
 `strcmp` İşlevleri duyarlıdır. `_stricmp`, `_wcsicmp`, ve `_mbsicmp` ilk bunları küçük formlarına dönüştürerek dizeleri karşılaştırmak. 'Z' arasında bulunan karakterler içeren iki dizeyi ve ASCII tablosundaki ' bir' ('[','`\`', '] ','`^`','`_`', ve ''') farklı şekilde, kendi çalışması bağlı olarak karşılaştırın. Örneğin, iki dizeyi `"ABCDE"` ve `"ABCD^"` karşılaştırma küçük harf ise bir yolu karşılaştırma (`"abcde"` > `"abcd^"`) ve diğer bir yol (`"ABCDE"` < `"ABCD^"`) karşılaştırma ise büyük.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`strcmp`|< string.h >|  
|`wcscmp`|< string.h > veya < wchar.h >|  
|`_mbscmp`|\<Mbstring.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_strcmp.c  
  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown dog jumps over the lazy fox";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
  
   // Case sensitive  
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );  
   result = strcmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof (tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof (tmp), "equal to" );  
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );  
  
   // Case insensitive (could use equivalent _stricmp)  
   result = _stricmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof (tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof (tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof (tmp), "equal to" );  
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );  
}  
```  
  
```Output  
Compare strings:  
   The quick brown dog jumps over the lazy fox  
   The QUICK brown dog jumps over the lazy fox  
  
   strcmp:   String 1 is greater than string 2  
   _stricmp:  String 1 is equal to string 2  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [_memicmp, _memicmp_l](../../c-runtime-library/reference/memicmp-memicmp-l.md)   
 [strcoll işlevleri](../../c-runtime-library/strcoll-functions.md)   
 [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)