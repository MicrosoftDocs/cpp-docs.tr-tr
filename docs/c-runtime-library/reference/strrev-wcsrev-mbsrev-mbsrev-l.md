---
title: _strrev, _wcsrev, _mbsrev, _mbsrev_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcsrev
- _mbsrev
- _strrev
- _mbsrev_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _strrev
- _ftcsrev
- _tcsrev
- mbsrev
- mbsrev_l
- _wcsrev_fstrrev
- _mbsrev
dev_langs: C++
helpviewer_keywords:
- _mbsrev_l function
- characters [C++], switching
- _mbsrev function
- strrev function
- _ftcsrev function
- strings [C++], reversing
- wcsrev function
- _strrev function
- mbsrev_l function
- reversing characters in strings
- ftcsrev function
- characters [C++], reversing order
- _wcsrev function
- mbsrev function
- tcsrev function
- _tcsrev function
ms.assetid: 87863e89-4fa0-421c-af48-25d8516fe72f
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 56a0fe307b03b7371818237b359e4840f1beef85
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="strrev-wcsrev-mbsrev-mbsrevl"></a>_strrev, _wcsrev, _mbsrev, _mbsrev_l
Bir dizenin karakter tersine çevirir.  
  
> [!IMPORTANT]
>  `_mbsrev`ve `_mbsrev_l` Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_strrev(  
   char *str   
);  
wchar_t *_wcsrev(  
   wchar_t *str   
);  
unsigned char *_mbsrev(  
   unsigned char *str   
);  
unsigned char *_mbsrev_l(  
   unsigned char *str,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `str`  
 Tersine çevirmek için null ile sonlandırılmış dize.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi değiştirilmiş dizesi olarak döndürür. Hiçbir değer döndürmeyen bir hatayı belirtmek için ayrılmıştır.  
  
## <a name="remarks"></a>Açıklamalar  
 `_strrev` İşlevi karakter sırasını tersine çevirir `string`. Sondaki boş karakter yerinde kalır. `_wcsrev`ve `_mbsrev` joker karakter ve çok baytlı karakter sürümleri `_strrev`. Bağımsız değişkenleri ve dönüş değerini `_wcsrev` joker karakter olan dizeleri; bu `_mbsrev` çok baytlı karakter dizeleri belirtilmiştir. İçin `_mbsrev`, her birden çok baytlı karakter bayt sırasını `string` değiştirilmez. Bu üç işlevler aynı şekilde aksi davranır.  
  
 `_mbsrev`parametreleri doğrular. Her iki `string1` veya `string2` null işaretçi açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `_mbsrev` döndürür `NULL` ve ayarlar `errno` için `EINVAL`. `_strrev`ve `_wcsrev` parametrelerini doğrulamaz.  
  
 Çıkış değerini ayarı tarafından etkilenen `LC_CTYPE` yerel kategori ayarı; bkz: [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Dosyalardan yok dışında bu işlevler sürümleri özdeş sahip `_l` sonekini kullan geçerli yerel ayar ve sahip olanları `_l` soneki yerine geçirilen yerel ayar parametresini kullanın. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
> [!IMPORTANT]
>  Bu işlevler taşması tehditlerine karşı savunmasız olabilir. Arabellek aşırı çalıştırmaları unwarranted ayrıcalıkların nedeni sistem saldırıları için kullanılabilir. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsrev`|`_strrev`|`_mbsrev`|`_wcsrev`|  
|**yok**|**yok**|`_mbsrev_l`|**yok**|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_strrev`|\<String.h >|  
|`_wcsrev`|\<String.h > veya \<wchar.h >|  
|`_mbsrev`, `_mbsrev_l`|\<Mbstring.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_strrev.c  
// This program checks a string to see  
// whether it is a palindrome: that is, whether  
// it reads the same forward and backward.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* string = "Able was I ere I saw Elba";  
   int result;  
  
   // Reverse string and compare (ignore case):  
   result = _stricmp( string, _strrev( _strdup( string ) ) );  
   if( result == 0 )  
      printf( "The string \"%s\" is a palindrome\n", string );  
   else  
      printf( "The string \"%s\" is not a palindrome\n", string );  
}  
```  
  
```Output  
The string "Able was I ere I saw Elba" is a palindrome  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcpy, wcscpy, _mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)