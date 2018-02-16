---
title: fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fwscanf_s
- _fscanf_s_l
- _fwscanf_s_l
- fscanf_s
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
- _fwscanf_s_l
- _fscanf_s_l
- fscanf_s
- _ftscanf_s_l
- _ftscanf_s
- fwscanf_s
dev_langs:
- C++
helpviewer_keywords:
- formatted data [C++], reading from streams
- _ftscanf_s_l function
- _fscanf_s_l function
- ftscanf_s function
- fwscanf_s function
- _ftscanf_s function
- data [CRT], reading from streams
- _fwscanf_s_l function
- fscanf_s function
- fwscanf_s_l function
- ftscanf_s_l function
- streams [C++], reading formatted data from
- fscanf_s_l function
ms.assetid: b6e88194-714b-4322-be82-1cc0b343fe01
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c37916febf85edbd612e96ff3cc383b77c63d664
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fscanfs-fscanfsl-fwscanfs-fwscanfsl"></a>fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l
Okuma akışı verilerden biçimlendirilmiş. Bu sürümleri [fscanf, _fscanf_l, fwscanf, _fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int fscanf_s(   
   FILE *stream,  
   const char *format [,  
   argument ]...   
);  
int _fscanf_s_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument ]...   
);  
int fwscanf_s(   
   FILE *stream,  
   const wchar_t *format [,  
   argument ]...   
);  
int _fwscanf_s_l(   
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ]...   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stream`  
 İşaretçi `FILE` yapısı.  
  
 `format`  
 Biçim denetimi dizesi.  
  
 `argument`  
 İsteğe bağlı bağımsız değişkenler.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her biri başarıyla dönüştürülür ve atanmış olan alan sayısını döndürür; dönüş değerini okumak ancak atanmamış alanları içermez. Dönüş değeri 0, hiçbir alan atandığını belirtir. Bir hata oluşursa veya dosya akışı sonuna ilk dönüştürmeden önce dönüş değeri `EOF` için `fscanf_s` ve `fwscanf_s`.  
  
 Bu işlevler kendi parametreleri doğrulayın. Varsa `stream` geçersiz dosya işaretçi veya `format` null işaretçi açıklandığı gibi bu işlevleri geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş `EOF` ve `errno` için `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `fscanf_s` İşlevi geçerli konumunu veri okuyan `stream` tarafından verilen konumları içine `argument` (varsa). Her bir `argument`, bir `format`'da tür tanımlayıcıyla karşılık gelen bir değişken türüne bir işaretçi olmalıdır. `format` giriş yorumu alanları ve aynı denetimleri form ve olarak işlev `format` bağımsız değişkeni için `scanf_s`; bkz [biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md) bir açıklaması için `format` .  `fwscanf_s` bir joker karakter sürümü `fscanf_s`; biçim bağımsız değişkeni `fwscanf_s` bir joker karakter dizesidir. Akış ANSI modunda açtıysanız bu işlevler aynı şekilde davranır. `fscanf_s` UNICODE akışı girişten şu anda desteklemiyor.  
  
 Daha güvenli işlevleri arasındaki temel fark (sahip `_s` soneki) ve diğer sürümleri daha güvenli işlevleri her karakter cinsinden boyutu gerektirir `c`, `C`, `s`, `S`, ve `[` türü değişkeni hemen ardından bağımsız değişken olarak geçirilen özgüdür. Daha fazla bilgi için bkz: [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) ve [sacnf genişlik belirtimi](../../c-runtime-library/scanf-width-specification.md).  
  
> [!NOTE]
>  Boyutu parametresi türünde `unsigned`değil `size_t`.  
  
 `_l` sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine iletilen yerel ayar parametresini kullanmaları hariç aynıdır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ftscanf_s`|`fscanf_s`|`fscanf_s`|`fwscanf_s`|  
|`_ftscanf_s_l`|`_fscanf_s_l`|`_fscanf_s_l`|`_fwscanf_s_l`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`fscanf_s`, `_fscanf_s_l`|\<stdio.h >|  
|`fwscanf_s`, `_fwscanf_s_l`|\<stdio.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_fscanf_s.c  
// This program writes formatted  
// data to a file. It then uses fscanf to  
// read the various data back from the file.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long l;  
   float fp;  
   char s[81];  
   char c;  
  
   errno_t err = fopen_s( &stream, "fscanf.out", "w+" );  
   if( err )  
      printf_s( "The file fscanf.out was not opened\n" );  
   else  
   {  
      fprintf_s( stream, "%s %ld %f%c", "a-string",   
               65000, 3.14159, 'x' );  
      // Set pointer to beginning of file:  
      fseek( stream, 0L, SEEK_SET );  
  
      // Read data back from file:  
      fscanf_s( stream, "%s", s, _countof(s) );  
      fscanf_s( stream, "%ld", &l );  
  
      fscanf_s( stream, "%f", &fp );  
      fscanf_s( stream, "%c", &c, 1 );  
  
      // Output data read:  
      printf( "%s\n", s );  
      printf( "%ld\n", l );  
      printf( "%f\n", fp );  
      printf( "%c\n", c );  
  
      fclose( stream );  
   }  
}  
```  
  
```Output  
a-string  
65000  
3.141590  
x  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](../../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)   
 [fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)   
 [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)   
 [fscanf, _fscanf_l, fwscanf, _fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)