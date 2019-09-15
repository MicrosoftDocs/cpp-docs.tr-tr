---
title: vfscanf, vfwscanf
ms.date: 11/04/2016
api_name:
- vfwscanf
- vfscanf
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
- vfwscanf
- _vftscanf
- vfscanf
ms.assetid: c06450ef-03f1-4d24-a8ac-d2dd98847918
ms.openlocfilehash: 72591c9fa91855745f45f3f77c88dd0ed5b001a0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70945516"
---
# <a name="vfscanf-vfwscanf"></a>vfscanf, vfwscanf

Bir akıştan biçimlendirilen verileri okur. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [vfscanf_s, vfwscanf_s](vfscanf-s-vfwscanf-s.md).

## <a name="syntax"></a>Sözdizimi

```C
int vfscanf(
   FILE *stream,
   const char *format,
   va_list argptr
);
int vfwscanf(
   FILE *stream,
   const wchar_t *format,
   va_list argptr
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

*format*<br/>
Biçim denetimi dizesi.

*Arglist*<br/>
Değişken bağımsız değişken listesi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, başarıyla dönüştürülen ve atanan alanların sayısını döndürür; dönüş değeri, okunan ancak atanmamış alanları içermez. 0 dönüş değeri hiçbir alan atanmadığını gösterir. Bir hata oluşursa veya dosya akışının sonuna ilk dönüştürmeden önce ulaşılırsa, **vfscanf** ve **vfwscanf**için dönüş değeri **EOF** olur.

Bu işlevler, parametrelerini doğrular. *Stream* veya *Format* null Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **EOF** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**Vfscanf** işlevi, *akışın* geçerli konumundaki verileri *Arglist* bağımsız değişken listesi tarafından verilen konumlara okur. Listedeki her bağımsız değişken, *biçimdeki*bir tür belirticisine karşılık gelen bir tür değişkenine bir işaretçi olmalıdır. *Format* , giriş alanlarının yorumunu denetler ve **scanf**için *Format* bağımsız değişkeniyle aynı forma ve işleve sahiptir; *biçimin*açıklaması için bkz. [scanf](scanf-scanf-l-wscanf-wscanf-l.md) .

**vfwscanf** , **vfscanf**; öğesinin geniş karakterli bir sürümüdür. **vfwscanf** biçim bağımsız değişkeni, geniş karakterli bir dizedir. Bu işlevler akış ANSI modunda açılırsa aynı şekilde davranır. **vfscanf** UNICODE akışından girişi desteklemez.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vftscanf**|**vfscanf**|**vfscanf**|**vfwscanf**|

Daha fazla bilgi için bkz. [Biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**vfscanf**|\<stdio. h >|
|**vfwscanf**|\<stdio. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_vfscanf.c
// compile with: /W3
// This program writes formatted
// data to a file. It then uses vfscanf to
// read the various data back from the file.

#include <stdio.h>
#include <stdarg.h>

FILE *stream;

int call_vfscanf(FILE * istream, char * format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vfscanf(istream, format, arglist);
    va_end(arglist);
    return result;
}

int main(void)
{
    long l;
    float fp;
    char s[81];
    char c;

    if (fopen_s(&stream, "vfscanf.out", "w+") != 0)
    {
        printf("The file vfscanf.out was not opened\n");
    }
    else
    {
        fprintf(stream, "%s %ld %f%c", "a-string",
            65000, 3.14159, 'x');
        // Security caution!
        // Beware loading data from a file without confirming its size,
        // as it may lead to a buffer overrun situation.

        // Set pointer to beginning of file:
        fseek(stream, 0L, SEEK_SET);

        // Read data back from file:
        call_vfscanf(stream, "%s %ld %f%c", s, &l, &fp, &c);

        // Output data read:
        printf("%s\n", s);
        printf("%ld\n", l);
        printf("%f\n", fp);
        printf("%c\n", c);

        fclose(stream);
    }
}
```

```Output
a-string
65000
3.141590
x
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)<br/>
[vfscanf_s, vfwscanf_s](vfscanf-s-vfwscanf-s.md)<br/>
