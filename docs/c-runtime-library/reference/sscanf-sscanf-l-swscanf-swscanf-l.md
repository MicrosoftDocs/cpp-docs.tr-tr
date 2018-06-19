---
title: sscanf, _sscanf_l, swscanf, _swscanf_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- swscanf
- sscanf
- _sscanf_l
- _swscanf_l
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
- _sscanf_l
- _stscanf
- swscanf
- _stscanf_l
- sscanf
- _swscanf_l
dev_langs:
- C++
helpviewer_keywords:
- swscanf function
- _stscanf function
- sscanf function
- _stscanf_l function
- _sscanf_l function
- _swscanf_l function
- swscanf_l function
- strings [C++], reading data from
- stscanf function
- reading data, strings
- strings [C++], reading
- sscanf_l function
- stscanf_l function
ms.assetid: c2dcf0d2-9798-499f-a4a8-06f7e2b9a80c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ac67b27564f694631977fd21c96922132b633e2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413612"
---
# <a name="sscanf-sscanfl-swscanf-swscanfl"></a>sscanf, _sscanf_l, swscanf, _swscanf_l

Bir dizeden veri okuma biçimlendirilmiş. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md).

## <a name="syntax"></a>Sözdizimi

```C
int sscanf(
   const char *buffer,
   const char *format [,
   argument ] ...
);
int _sscanf_l(
   const char *buffer,
   const char *format,
   locale_t locale [,
   argument ] ...
);
int swscanf(
   const wchar_t *buffer,
   const wchar_t *format [,
   argument ] ...
);
int _swscanf_l(
   const wchar_t *buffer,
   const wchar_t *format,
   locale_t locale [,
   argument ] ...
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Depolanan verileri

*Biçimi*<br/>
Biçim denetimi dizesi. Daha fazla bilgi için bkz: [biçim belirtimleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler

*Yerel ayar*<br/>
Kullanılacak yerel ayar

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri başarıyla dönüştürülür ve atanan alan sayısını döndürür; dönüş değerini okumak ancak atanmamış alanları içermez. Dönüş değeri 0, hiçbir alan atandığını belirtir. Dönüş değeri **EOF** bir hata için veya dize sonu ilk dönüştürmeden önce ulaşılırsa.

Varsa *arabellek* veya *biçimi* olan bir **NULL** işaretçi, geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve **errno** için **EINVAL**.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Sscanf** işlevi verileri okur *arabellek* her tarafından belirtilen konuma *bağımsız değişkeni*. Her *bağımsız değişkeni* bir tür belirteci karşılık gelen türüne sahip bir değişken için bir işaretçi olmalıdır *biçimi*. *Biçimi* giriş yorumu alanları ve aynı bağımsız değişkeni denetimleri form ve olarak işlev *biçimi* bağımsız değişkeni için **scanf** işlevi. Kopyalama çakışma dizeleri arasında yer alıyorsa, tanımlanmamış bir davranıştır.

> [!IMPORTANT]
> Bir dizeyle'ne zaman okuma **sscanf**, her zaman için bir genişliği belirtmeniz **%s** biçimi (örneğin, **"% 32s"** yerine **"%s"**); Aksi takdirde , düzgün biçimlendirilmemiş giriş arabellek taşması kolayca neden olabilir.

**swscanf** bir joker karakter sürümü **sscanf**; bağımsız değişkenleri **swscanf** joker karakter dizelerdir. **sscanf** onaltılık birden çok baytlı karakterler işlemez. **swscanf** Unicode tam genişlikli onaltılık veya "uyumluluk bölge" karakterleri işlemez. Aksi takdirde, **swscanf** ve **sscanf** aynı şekilde davranır.

Bu işlevleri sürümlerini **_l** soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stscanf**|**sscanf**|**sscanf**|**swscanf**|
|**_stscanf_l**|**_sscanf_l**|**_sscanf_l**|**_swscanf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**sscanf**, **_sscanf_l**|\<stdio.h >|
|**swscanf**, **_swscanf_l**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_sscanf.c
// compile with: /W3
// This program uses sscanf to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>

int main( void )
{
   char  tokenstring[] = "15 12 14...";
   char  s[81];
   char  c;
   int   i;
   float fp;

   // Input various data from tokenstring:
   // max 80 character string:
   sscanf( tokenstring, "%80s", s ); // C4996
   sscanf( tokenstring, "%c", &c );  // C4996
   sscanf( tokenstring, "%d", &i );  // C4996
   sscanf( tokenstring, "%f", &fp ); // C4996
   // Note: sscanf is deprecated; consider using sscanf_s instead

   // Output the data read
   printf( "String    = %s\n", s );
   printf( "Character = %c\n", c );
   printf( "Integer:  = %d\n", i );
   printf( "Real:     = %f\n", fp );
}
```

```Output
String    = 15
Character = 1
Integer:  = 15
Real:     = 15.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l](snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)<br/>
