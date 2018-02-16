---
title: fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _fprintf_s_l
- fwprintf_s
- fprintf_s
- _fwprintf_s_l
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
- _ftprintf_s
- fprintf_s
- fwprintf_s
dev_langs:
- C++
helpviewer_keywords:
- ftprintf_s_l function
- ftprintf_s function
- _fprintf_s_l function
- _ftprintf_s function
- _ftprintf_s_l function
- fwprintf_s_l function
- fwprintf_s function
- fprintf_s_l function
- fprintf_s function
- _fwprintf_s_l function
- print formatted data to streams
ms.assetid: 16067c3c-69ce-472a-8272-9aadf1f5beed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 85877d6bbab237c4c852ef7babce38b936e598fc
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fprintfs-fprintfsl-fwprintfs-fwprintfsl"></a>fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l
Akış biçimlendirilmiş verileri yazdırma. Sürümleri bunlar [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int fprintf_s(   
   FILE *stream,  
   const char *format [,  
   argument_list ]  
);  
int _fprintf_s_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument_list ]  
);  
int fwprintf_s(   
   FILE *stream,  
   const wchar_t *format [,  
   argument_list ]  
);  
int _fwprintf_s_l(   
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale [,  
   argument_list ]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stream`  
 İşaretçi `FILE` yapısı.  
  
 `format`  
 Biçim denetimi dizesi.  
  
 `argument_list`  
 İsteğe bağlı bağımsız değişkenler için biçim dizesi.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `fprintf_s` yazılan bayt sayısını döndürür. `fwprintf_s` yazılan geniş karakter sayısını döndürür. Çıkış hata oluştuğunda bu işlevlerin her biri negatif bir değer yerine döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `fprintf_s` biçimlendirir ve bir dizi karakter ve değerlerini çıktıya yazdırır `stream`. Her bağımsız değişkeninde `argument_list` (varsa) dönüştürülür ve çıktı içinde karşılık gelen biçimi belirtimlerine göre `format`. `format` Bağımsız değişkeni kullanır [biçim belirtim Sözdizimi printf ve wprintf işlevleri için](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
 `fwprintf_s` bir joker karakter sürümü `fprintf_s`; `fwprintf_s`, `format` bir joker karakter dizesidir. Akış ANSI modunda açtıysanız bu işlevler aynı şekilde davranır. `fprintf_s` şu anda çıktı bir UNICODE akışa desteklemiyor.  
  
 Bu işlevleri sürümlerini `_l` soneki, geçerli yerel yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.  
  
> [!IMPORTANT]
>  Emin `format` kullanıcı tanımlı bir dize değil.  
  
 Güvenli olmayan sürümleri gibi (bkz [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)), bu işlevler parametrelerini doğrulayın ve açıklandığı gibi geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md), her iki `stream` veya `format` null işaretçi. Biçim dizesi de doğrulanır. Tüm bilinmeyen veya hatalı biçimlendirilmiş biçimlendirme tanımlayıcıları varsa, bu işlevler geçersiz parametre özel durum oluşturur. Devam etmek için yürütülmesine izin veriliyorsa tüm durumlarda işlevleri -1 döndürür. ve `errno` için `EINVAL`. Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ftprintf_s`|`fprintf_s`|`fprintf_s`|`fwprintf_s`|  
|`_ftprintf_s_l`|`_fprintf_s_l`|`_fprintf_s_l`|`_fwprintf_s_l`|  
  
 Daha fazla bilgi için bkz: [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`fprintf_s`, `_fprintf_s_l`|\<stdio.h >|  
|`fwprintf_s`, `_fwprintf_s_l`|\<stdio.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_fprintf_s.c  
// This program uses fprintf_s to format various  
// data and print it to the file named FPRINTF_S.OUT. It  
// then displays FPRINTF_S.OUT on the screen using the system  
// function to invoke the operating-system TYPE command.  
  
#include <stdio.h>  
#include <process.h>  
  
FILE *stream;  
  
int main( void )  
{  
   int    i = 10;  
   double fp = 1.5;  
   char   s[] = "this is a string";  
   char   c = '\n';  
  
   fopen_s( &stream, "fprintf_s.out", "w" );  
   fprintf_s( stream, "%s%c", s, c );  
   fprintf_s( stream, "%d\n", i );  
   fprintf_s( stream, "%f\n", fp );  
   fclose( stream );  
   system( "type fprintf_s.out" );  
}  
```  
  
```Output  
this is a string  
10  
1.500000  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf, _fscanf_l, fwscanf, _fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)