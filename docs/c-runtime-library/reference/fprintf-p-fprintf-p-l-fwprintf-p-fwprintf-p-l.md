---
description: 'Hakkında daha fazla bilgi edinin: _fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l'
title: _fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l
ms.date: 11/04/2016
api_name:
- _fwprintf_p
- _fprintf_p_l
- _fwprintf_p_l
- _fprintf_p
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fprintf_p
- _ftprintf_p
- fwprintf_p
- _fwprintf_p
- fprintf_p
- ftprintf_p
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
ms.openlocfilehash: 543589a864c19e1c1fddde0c6837f680903666cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178634"
---
# <a name="_fprintf_p-_fprintf_p_l-_fwprintf_p-_fwprintf_p_l"></a>_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l

Biçimli verileri bir akışa yazdırır.

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

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

*formatını*<br/>
Biçim denetimi dizesi.

*değişkendir*<br/>
İsteğe bağlı bağımsız değişkenler.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_fprintf_p** ve **_fwprintf_p** , yazılan karakter sayısını döndürür veya bir çıkış hatası oluştuğunda negatif bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**_fprintf_p** biçimlendirir ve çıkış *akışına* bir dizi karakter ve değer yazdırır. Her bir işlev *bağımsız değişkeni* (varsa) dönüştürülür ve karşılık *gelen biçim belirtimine göre çıkış.* **_Fprintf_p** için, *Biçim* bağımsız değişkeni aynı söz dizimine sahiptir ve **_printf_p** sahip olduğu ' ı kullanır. Bu işlevler konumsal parametreleri destekler, yani biçim dizesi tarafından kullanılan parametrelerin sırası değiştirilebilir. Konumsal parametreler hakkında daha fazla bilgi için bkz. [Printf_p Konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md).

**_fwprintf_p** , **_fprintf_p** geniş karakterli bir sürümüdür; **_fwprintf_p**, *Biçim* geniş karakterli bir dizedir. Bu işlevler akış ANSI modunda açılırsa aynı şekilde davranır. **_fprintf_p** Şu anda UNICODE bir akışa çıktıyı desteklememektedir.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli yerel ayar yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

> [!IMPORTANT]
> *Biçimin* Kullanıcı tanımlı bir dize olmadığından emin olun.

Güvenli olmayan sürümler gibi (bkz. [fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)), bu işlevler parametreleri doğrular ve [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır; *Stream* veya *Format* null işaretçisiyse veya bilinmeyen ya da hatalı biçimlendirilmiş biçimlendirme belirticileri varsa. Yürütmenin devam etmesine izin veriliyorsa, işlevler-1 döndürür ve **errno** , **EINVAL** olarak ayarlanır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_ftprintf_p**|**_fprintf_p**|**_fprintf_p**|**_fwprintf_p**|
|**_ftprintf_p_l**|**_fprintf_p_l**|**_fprintf_p_l**|**_fwprintf_p_l**|

Daha fazla bilgi için bkz. [Biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fprintf_p**, **_fprintf_p_l**|\<stdio.h>|
|**_fwprintf_p**, **_fwprintf_p_l**|\<stdio.h> veya \<wchar.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[printf_p Konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
[_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l](cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)<br/>
[_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)<br/>
[printf_p Konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
[fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)<br/>
