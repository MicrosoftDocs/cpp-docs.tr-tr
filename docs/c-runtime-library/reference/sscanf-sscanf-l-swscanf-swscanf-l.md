---
title: sscanf, _sscanf_l, swscanf, _swscanf_l
ms.date: 08/29/2019
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
ms.openlocfilehash: ac8bc14fed554c2ea5cede7f37c1dc49f4740bf3
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177425"
---
# <a name="sscanf-_sscanf_l-swscanf-_swscanf_l"></a>sscanf, _sscanf_l, swscanf, _swscanf_l

Bir dizeden biçimlendirilen verileri okur. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md).

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

*arabelleğin*<br/>
Depolanan veriler

*format*<br/>
Biçim denetimi dizesi. Daha fazla bilgi için bkz. [Biçim belirtimleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*değişkendir*<br/>
İsteğe bağlı bağımsız değişkenler

*ayarlar*<br/>
Kullanılacak yerel ayar

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, başarıyla dönüştürülen ve atanan alanların sayısını döndürür; dönüş değeri, okunan ancak atanmamış alanları içermez. 0 dönüş değeri hiçbir alan atanmadığını gösterir. Dönüş değeri bir hata için veya ilk dönüştürmeden önce dizenin sonuna ulaşılırsa.

*Arabellek* veya *Biçim* **null** işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür ve **errno** , **EINVAL**olarak ayarlanır.

Bu ve diğer hata kodları hakkında bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Sscanf** işlevi, *arabellekteki* verileri her *bağımsız değişken*tarafından verilen konuma okur. Her *bağımsız değişken* , *biçimdeki*bir tür belirticisine karşılık gelen türe sahip bir değişkene yönelik bir işaretçi olmalıdır. *Biçim* bağımsız değişkeni, giriş alanlarının yorumunu denetler ve **scanf** işlevinin *Format* bağımsız değişkeniyle aynı forma ve işleve sahiptir. Çakışan dizeler arasında kopyalama gerçekleşmesi durumunda davranış tanımsızdır.

Scanf türü alan karakterleri hakkında daha fazla bilgi için bkz. [scanf Type alan karakterleri](../scanf-type-field-characters.md). Scanf biçim belirtimi alanları hakkında daha fazla bilgi için bkz. [Biçim belirtimi alanları](../format-specification-fields-scanf-and-wscanf-functions.md).

> [!IMPORTANT]
> **Sscanf**ile bir dize okurken, her zaman **% s** biçimi için bir genişlik belirleyin (örneğin, "% **s"** yerine **"% 32S"** ); Aksi halde, düzensiz biçimli giriş, arabellek taşmasına kolayca neden olabilir.

**swscanf** , **sscanf**; öğesinin geniş karakterli bir sürümüdür. **swscanf** bağımsız değişkenleri geniş karakterli dizelerdir. **sscanf** çok baytlı onaltılık karakterleri işlemez. **swscanf** , Unicode tam genişlikli onaltılı veya "uyumluluk bölgesi" karakterlerini işlemez. Aksi halde, **swscanf** ve **sscanf** aynı şekilde davranır.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stscanf**|**sscanf**|**sscanf**|**swscanf**|
|**_stscanf_l**|**_sscanf_l**|**_sscanf_l**|**_swscanf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**sscanf**, **_sscanf_l**|\<stdio. h >|
|**swscanf**, **_swscanf_l**|\<stdio. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
