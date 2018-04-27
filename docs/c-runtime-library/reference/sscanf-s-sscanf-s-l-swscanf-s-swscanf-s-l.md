---
title: sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _sscanf_s_l
- sscanf_s
- _swscanf_s_l
- swscanf_s
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
- _stscanf_s
- sscanf_s
- swscanf_s
- _swscanf_s_l
- _stscanf_s_l
- _sscanf_s_l
dev_langs:
- C++
helpviewer_keywords:
- stscanf_s_l function
- stscanf_s function
- swscanf_s function
- swscanf_s_l function
- sscanf_s_l function
- _stscanf_s_l function
- strings [C++], reading data from
- sscanf_s function
- _swscanf_s_l function
- _stscanf_s function
- reading data, strings
- strings [C++], reading
- _sscanf_s_l function
ms.assetid: 956e65c8-00a5-43e8-a2f2-0f547ac9e56c
caps.latest.revision: 30
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 995cf583751903527fec9518b81b4048844d4f52
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="sscanfs-sscanfsl-swscanfs-swscanfsl"></a>sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l

Bir dizeden veri okuma biçimlendirilmiş. Bu sürümleri [sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
int sscanf_s(
   const char *buffer,
   const char *format [,
   argument ] ...
);
int _sscanf_s_l(
   const char *buffer,
   const char *format,
   locale_t locale [,
   argument ] ...
);
int swscanf_s(
   const wchar_t *buffer,
   const wchar_t *format [,
   argument ] ...
);
int _swscanf_s_l(
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
Biçim denetimi dizesi. Daha fazla bilgi için bkz: [biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler

*Yerel ayar*<br/>
Kullanılacak yerel ayar

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri başarıyla dönüştürülür ve atanmış olan alan sayısını döndürür; dönüş değerini okumak ancak atanmamış alanları içermez. Dönüş değeri 0, hiçbir alan atandığını belirtir. Dönüş değeri **EOF** bir hata için veya dize sonu ilk dönüştürmeden önce ulaşılırsa.

Varsa *arabellek* veya *biçimi* olan bir **NULL** işaretçi, geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve **errno** için **EINVAL**

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Sscanf_s** işlevi verileri okur *arabellek* her tarafından verilen bir konuma *bağımsız değişkeni*. Biçim dizesi bağımsız bir tür belirteci karşılık gelen bir türe sahip değişkenler işaretçiler belirtin *biçimi*. Daha az güvenli sürüm aksine [sscanf](sscanf-sscanf-l-swscanf-swscanf-l.md), türü alan karakterleri kullandığınızda bir arabellek boyutu parametresi gereklidir **c**, **C**, **s**, **S**, veya dize içine denetim kümeleri **[]**. Arabellek boyutu karakter ek bir parametre bunu gerektiren hemen her arabellek parametre sonra sağlanmalıdır. Örneğin, bir dizeye okuyorsanız arabellek boyutu için bu dizeyi şu şekilde geçirilir:

```C
wchar_t ws[10];
swscanf_s(in_str, L"%9s", ws, (unsigned)_countof(ws)); // buffer size is 10, width specification is 9
```

Arabellek boyutu sonlandırma null içerir. Genişlik belirtimi alanında okunduktan belirteci belleğe sığmayacak emin olmak için kullanılabilir. Genişlik belirtimi alan kullanılır ve okunan belirteci arabellek sığmayacak kadar büyük ise, hiçbir şey bu arabelleğe yazılır.

Karakterler söz konusu olduğunda, tek bir karakter aşağıdaki gibi okunabilir:

```C
wchar_t wc;
swscanf_s(in_str, L"%c", &wc, 1);
```

Bu örnek giriş dizesi bir tek karakteri okur ve bir joker karakter arabelleğinde depolar. Null olmayan sonlandırılmış dizeler için birden çok karakter okurken imzasız tamsayılar genişlik belirtimi ve arabellek boyutu kullanılır.

```C
char c[4];
sscanf_s(input, "%4c", &c, (unsigned)_countof(c)); // not null terminated
```

Daha fazla bilgi için bkz: [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) ve [scanf türü alan karakterleri](../../c-runtime-library/scanf-type-field-characters.md).

> [!NOTE]
> Boyutu parametresi türünde **imzasız**değil **size_t**. 64-bit hedefler için derlerken dönüştürmek için bir statik atama kullanın **_countof** veya **sizeof** doğru boyutta sonuçları.

*Biçimi* giriş yorumu alanları ve aynı bağımsız değişkeni denetimleri form ve olarak işlev *biçimi* bağımsız değişkeni için **scanf_s** işlevi. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

**swscanf_s** bir joker karakter sürümü **sscanf_s**; bağımsız değişkenleri **swscanf_s** joker karakter dizelerdir. **sscanf_s** onaltılık birden çok baytlı karakterler işlemez. **swscanf_s** Unicode tam genişlikli onaltılık veya "uyumluluk bölge" karakterleri işlemez. Aksi takdirde, **swscanf_s** ve **sscanf_s** aynı şekilde davranır.

Bu işlevleri sürümlerini **_l** soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullandıkları dışında aynıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stscanf_s**|**sscanf_s**|**sscanf_s**|**swscanf_s**|
|**_stscanf_s_l**|**_sscanf_s_l**|**_sscanf_s_l**|**_swscanf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**sscanf_s**, **_sscanf_s_l**|\<stdio.h >|
|**swscanf_s**, **_swscanf_s_l**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_sscanf_s.c
// This program uses sscanf_s to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char  tokenstring[] = "15 12 14...";
   char  s[81];
   char  c;
   int   i;
   float fp;

   // Input various data from tokenstring:
   // max 80 character string plus NULL terminator
   sscanf_s( tokenstring, "%s", s, (unsigned)_countof(s) );
   sscanf_s( tokenstring, "%c", &c, (unsigned)sizeof(char) );
   sscanf_s( tokenstring, "%d", &i );
   sscanf_s( tokenstring, "%f", &fp );

   // Output the data read
   printf_s( "String    = %s\n", s );
   printf_s( "Character = %c\n", c );
   printf_s( "Integer:  = %d\n", i );
   printf_s( "Real:     = %f\n", fp );
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
