---
title: _fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fwprintf_p
- _fprintf_p_l
- _fwprintf_p_l
- _fprintf_p
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
- _fprintf_p
- _ftprintf_p
- fwprintf_p
- _fwprintf_p
- fprintf_p
- ftprintf_p
dev_langs:
- C++
helpviewer_keywords:
- fprintf_p_l function
- fprintf_p function
- _fprintf_p_l function
- _fprintf_p function
- _ftprintf_p_l function
- streams, printing formatted data to
- _fwprintf_p function
- fwprintf_p function
- _ftprintf_p function
- _fwprintf_p_l function
- ftprintf_p function
- printing [C++], formatted data to streams
- ftprintf_p_l function
- fwprintf_p_l function
ms.assetid: 46b082e1-45ba-4383-9ee4-97015aa50bc6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef748590f412afc10b5046691c982ed1d5ccabb8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fprintfp-fprintfpl-fwprintfp-fwprintfpl"></a>_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l

Baskı siparişi veri akış biçimlendirilmiş.

## <a name="syntax"></a>Sözdizimi

```C
int _fprintf_p(
   FILE *stream,
   const char *format [,
   argument ]...
);
int _fprintf_p_l(
   FILE *stream,
   const char *format,
   locale_t locale [,
   argument ]...
);
int _fwprintf_p(
   FILE *stream,
   const wchar_t *format [,
   argument ]...
);
int _fwprintf_p_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale [,
   argument ]...
);
```

### <a name="parameters"></a>Parametreler

*Akış*<br/>
İşaretçi **dosya** yapısı.

*Biçimi*<br/>
Biçim denetimi dizesi.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_fprintf_p** ve **_fwprintf_p** yazılan karakterlerin sayısını döndürür veya çıkış hata oluştuğunda negatif bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**_fprintf_p** biçimlendirir ve bir dizi karakter ve değerlerini çıktıya yazdırır *akış*. Her işlev *bağımsız değişkeni* (varsa) dönüştürülür ve çıktı içinde karşılık gelen biçimi belirtimlerine göre *biçimi*. İçin **_fprintf_p**, *biçimi* bağımsız değişkenini içeriyor aynı sözdizimi ve sahip olarak kullanımı **_printf_p**. Bu işlevler biçim dizesi tarafından kullanılan parametreler sırası değiştirilebilir anlamı konumsal parametreler destekler. Konumsal parametreler hakkında daha fazla bilgi için bkz: [printf_p konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md).

**_fwprintf_p** bir joker karakter sürümü **_fprintf_p**; **_fwprintf_p**, *biçimi* bir joker karakter dizesidir. Akış ANSI modunda açtıysanız bu işlevler aynı şekilde davranır. **_fprintf_p** çıktı bir UNICODE akışa şu anda desteklemiyor.

Bu işlevleri sürümlerini **_l** soneki, geçerli yerel yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil.

Güvenli olmayan sürümleri gibi (bkz [fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)), bu işlevler parametrelerini doğrulayın ve açıklandığı gibi geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md), her iki *akış* veya *biçimi* null işaretçi veya bilinmeyen ya da hatalı oluşturulmuş tüm biçimlendirme tanımlayıcıları varsa. Devam etmek için yürütülmesine izin veriliyorsa, işlevleri -1 döndürür ve **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_ftprintf_p**|**_fprintf_p**|**_fprintf_p**|**_fwprintf_p**|
|**_ftprintf_p_l**|**_fprintf_p_l**|**_fprintf_p_l**|**_fwprintf_p_l**|

Daha fazla bilgi için bkz: [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fprintf_p**, **_fprintf_p_l**|\<stdio.h >|
|**_fwprintf_p**, **_fwprintf_p_l**|\<stdio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fprintf_p.c
// This program uses _fprintf_p to format various
// data and print it to the file named FPRINTF_P.OUT. It
// then displays FPRINTF_P.OUT on the screen using the system
// function to invoke the operating-system TYPE command.
//

#include <stdio.h>
#include <process.h>

int main( void )
{
    FILE    *stream = NULL;
    int     i = 10;
    double  fp = 1.5;
    char    s[] = "this is a string";
    char    c = '\n';

    // Open the file
    if ( fopen_s( &stream, "fprintf_p.out", "w" ) == 0)
    {
        // Format and print data
        _fprintf_p( stream, "%2$s%1$c", c, s );
        _fprintf_p( stream, "%d\n", i );
        _fprintf_p( stream, "%f\n", fp );

        // Close the file
        fclose( stream );
    }

    // Verify our data
    system( "type fprintf_p.out" );
}
```

```Output
this is a string
10
1.500000
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[printf_p Konumsal Parametreler](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
[_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l](cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)<br/>
[_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)<br/>
[printf_p Konumsal Parametreler](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
[fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)<br/>
