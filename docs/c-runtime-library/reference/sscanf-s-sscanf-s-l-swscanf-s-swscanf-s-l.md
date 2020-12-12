---
description: 'Hakkında daha fazla bilgi edinin: sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l'
title: sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l
ms.date: 11/04/2016
api_name:
- _sscanf_s_l
- sscanf_s
- _swscanf_s_l
- swscanf_s
api_location:
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _stscanf_s
- sscanf_s
- swscanf_s
- _swscanf_s_l
- _stscanf_s_l
- _sscanf_s_l
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
ms.openlocfilehash: 3f61292932ea6b77b4694588726094d78b8405cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97171315"
---
# <a name="sscanf_s-_sscanf_s_l-swscanf_s-_swscanf_s_l"></a>sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l

Bir dizeden biçimlendirilen verileri okur. [Sscanf, _sscanf_l, swscanf _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md) bu SÜRÜMLERINDE, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

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

*arabelleğin*<br/>
Depolanan veriler

*formatını*<br/>
Biçim denetimi dizesi. Daha fazla bilgi için bkz. [Biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*değişkendir*<br/>
İsteğe bağlı bağımsız değişkenler

*locale*<br/>
Kullanılacak yerel ayar

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, başarıyla dönüştürülen ve atanan alanların sayısını döndürür; dönüş değeri, okunan ancak atanmamış alanları içermez. 0 dönüş değeri hiçbir alan atanmadığını gösterir. Dönüş değeri bir hata **için veya** ilk dönüştürmeden önce dizenin sonuna ulaşılırsa.

*Arabellek* veya *Biçim* **null** işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür ve **errno** 'ı **EINVAL** olarak ayarlar

Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Sscanf_s** işlevi, *arabellekteki* verileri her *bağımsız değişken* tarafından verilen konuma okur. Biçim dizesinden sonraki bağımsız değişkenler, *biçimde* bir tür belirticisine karşılık gelen bir türe sahip değişkenlere işaretçiler belirtir. Daha az güvenli sürüm olan [sscanf](sscanf-sscanf-l-swscanf-swscanf-l.md)'den farklı olarak, **[]** içinde bulunan **c**, **c**, **s**, **s** veya dize denetim kümelerini tür alan karakterlerini kullandığınızda bir arabellek boyutu parametresi gerekir. Karakter cinsinden arabellek boyutu, her bir arabellek parametresinden hemen sonra ek bir parametre olarak sağlanmalıdır. Örneğin, bir dizeye okuyorsanız, bu dize için arabellek boyutu aşağıdaki gibi geçirilir:

```C
wchar_t ws[10];
swscanf_s(in_str, L"%9s", ws, (unsigned)_countof(ws)); // buffer size is 10, width specification is 9
```

Arabellek boyutu, Sonlandırıcı null değerini içerir. Bir genişlik belirtimi alanı, okunan belirtecin arabelleğe sığmasını sağlamak için kullanılabilir. Bir genişlik belirtimi alanı kullanılmıyorsa ve okunan belirteç arabelleğe sığmayacak kadar büyük ise, bu arabelleğe hiçbir şey yazılmaz.

Karakterler söz konusu olduğunda, tek bir karakter aşağıdaki gibi okunabilir:

```C
wchar_t wc;
swscanf_s(in_str, L"%c", &wc, 1);
```

Bu örnek, giriş dizesinden tek bir karakteri okur ve sonra geniş karakterli bir arabellekte depolar. Null olmayan sonlandırılmış dizeler için birden çok karakter okuduğunuzda, işaretsiz tamsayılar genişlik belirtimi ve arabellek boyutu olarak kullanılır.

```C
char c[4];
sscanf_s(input, "%4c", &c, (unsigned)_countof(c)); // not null terminated
```

Daha fazla bilgi için bkz. [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) ve [scanf türü alan karakterleri](../../c-runtime-library/scanf-type-field-characters.md).

> [!NOTE]
> Boyut parametresi **`unsigned`** **size_t** değil türündedir. 64 bitlik hedefler için derlerken, **_countof** veya **`sizeof`** sonuçları doğru boyuta dönüştürmek için statik bir tür kullanın.

*Biçim* bağımsız değişkeni, giriş alanlarının yorumunu denetler ve **scanf_s** işlevi için *Biçim* bağımsız değişkeniyle aynı forma ve işleve sahiptir. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

**swscanf_s** , **sscanf_s** geniş karakterli bir sürümüdür; **swscanf_s** bağımsız değişkenler geniş karakterli dizelerdir. **sscanf_s** çok baytlı onaltılık karakterleri işlemez. **Swscanf_s** Unicode tam genişlikli onaltılı veya "uyumluluk bölgesi" karakterlerini işlemez. Aksi takdirde, **swscanf_s** ve **sscanf_s** aynı şekilde davranır.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stscanf_s**|**sscanf_s**|**sscanf_s**|**swscanf_s**|
|**_stscanf_s_l**|**_sscanf_s_l**|**_sscanf_s_l**|**_swscanf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**sscanf_s**, **_sscanf_s_l**|\<stdio.h>|
|**swscanf_s**, **_swscanf_s_l**|\<stdio.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
   // max 80 character string plus null terminator
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

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l](snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)<br/>
