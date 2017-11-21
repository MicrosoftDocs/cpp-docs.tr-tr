---
title: _sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _sprintf_p
- _swprintf_p_l
- _swprintf_p
- _sprintf_p_l
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
apitype: DLLExport
f1_keywords:
- _sprintf_p
- _swprintf_p_l
- _sprintf_p_l
- _swprintf_p
- sprintf_p
- swprint_p_l
- swprintf_p
- swprintf_p_l
dev_langs: C++
helpviewer_keywords:
- sprintf_p_l function
- swprintf_p function
- swprintf_p_l function
- _sprintf_p function
- _sprintf_p_l function
- _swprintf_p function
- sprintf_p function
- _stprintf_p function
- stprintf_p function
- _swprintf_p_l function
- stprintf_p_l function
- formatted text [C++]
- _stprintf_p_l function
ms.assetid: a2ae78e8-6b0c-48d5-87a9-ea2365b0693d
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 010b3f04509852012dac641aadeb4152d666898d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="sprintfp-sprintfpl-swprintfp-swprintfpl"></a>_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l
Biçimlendirilmiş verileri parametreleri biçim dizesi kullanılır order belirtme olanağı ile bir dizeye yazma.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _sprintf_p(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format [,  
   argument_list]  
);  
int _sprintf_p_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   locale_t locale [,  
   argument_list]  
);  
int _swprintf_p(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format [,  
   argument_list]  
);  
int _swprintf_p_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument_list]   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `buffer`  
 Çıktı için depolama konumu  
  
 `sizeOfBuffer`  
 Depolanacak maksimum karakter sayısı.  
  
 `format`  
 Biçim denetimi dizesi.  
  
 `argument_list`  
 İsteğe bağlı bağımsız değişkenler için biçim dizesi.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
 Daha fazla bilgi için bkz: [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yazılan karakter sayısını veya bir hata oluştuysa -1.  
  
## <a name="remarks"></a>Açıklamalar  
 `_sprintf_p` İşlevi biçimlendirir ve bir dizi karakter ve değerleri depolar `buffer`. Her bağımsız değişkeninde `argument_list` (varsa) dönüştürülür ve çıktı içinde karşılık gelen biçimi belirtimlerine göre `format`. `format` Bağımsız değişkeni kullanır [biçim belirtim Sözdizimi printf ve wprintf işlevleri için](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md). A `NULL` karakter yazılmış son karakter sonra eklenir. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır. Arasındaki farkı `_sprintf_p` ve `sprintf_s` olan `_sprintf_p` biçim dizesi bağımsız değişkenleri kullanıldığı sırayı belirten verir destekler konumsal parametreler. Daha fazla bilgi için bkz: [printf_p konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 `_swprintf_p`bir joker karakter sürümü `_sprintf_p`; işaretçi bağımsız değişkenleri `_swprintf_p` joker karakter dizelerdir. Kodlama hataları algılama `_swprintf_p` , farklı olabilir `_sprintf_p`. `_swprintf_p`ve `fwprintf_p` durumlar dışında aynı şekilde davranır `_swprintf_p` bir dize yerine bir hedef türü çıktısı Yazar `FILE`, ve `_swprintf_p` gerektirir `count` parametre olarak karakter sayısını belirtin yazılır. Bu işlevleri sürümlerini `_l` soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.  
  
 `_sprintf_p`depolanan bayt sayısını verir `buffer`, sonlandırma saymaz `NULL` karakter. `_swprintf_p`depolanan geniş karakter sayısını verir `buffer`, sonlandırma saymaz `NULL` geniş karakter. Varsa `buffer` veya `format` null işaretçi veya biçim dizesi geçersiz biçimlendirme karakterlerini içeriyorsa, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve `errno` için `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_stprintf_p`|`_sprintf_p`|`_sprintf_p`|`_swprintf_p`|  
|`_stprintf_p_l`|`_sprintf_p_l`|`_sprintf_p_l`|`_swprintf_p_l`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_sprintf_p`, `_sprintf_p_l`|\<stdio.h >|  
|`_swprintf_p`, `_swprintf_p_l`|\<stdio.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_sprintf_p.c  
// This program uses _sprintf_p to format various  
// data and place them in the string named buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
    char     buffer[200],  
            s[] = "computer", c = 'l';  
    int      i = 35,  
            j;  
    float    fp = 1.7320534f;  
  
    // Format and print various data:   
    j  = _sprintf_p( buffer, 200,  
                     "   String:    %s\n", s );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Character: %c\n", c );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Integer:   %d\n", i );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Real:      %f\n", fp );  
  
    printf( "Output:\n%s\ncharacter count = %d\n",   
            buffer, j );  
}  
```  
  
```Output  
Output:  
   String:    computer  
   Character: l  
   Integer:   35  
   Real:      1.732053  
  
character count = 79  
```  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_swprintf_p.c  
// This is the wide character example which  
// also demonstrates _swprintf_p returning  
// error code.  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    wchar_t buffer[BUFFER_SIZE];  
    int     len;  
  
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%2$s %1$d",  
                      0, L" marbles in your head.");  
    _printf_p( "Wrote %d characters\n", len );  
  
    // _swprintf_p fails because string contains WEOF (\xffff)  
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%s",   
                      L"Hello\xffff world" );  
    _printf_p( "Wrote %d characters\n", len );  
}  
```  
  
```Output  
Wrote 24 characters  
Wrote -1 characters  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [Printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, _sscanf_l, swscanf, _swscanf_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)   
 [vprintf işlevleri](../../c-runtime-library/vprintf-functions.md)   
 [printf_p konumsal Parametreler](../../c-runtime-library/printf-p-positional-parameters.md)