---
title: vfscanf_s, vfwscanf_s
ms.date: 11/04/2016
apiname:
- vfscanf_s
- vfwscanf_s
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
- vfscanf_s
- vfwscanf_s
- _vftscanf_s
ms.assetid: 9b0133f0-9a18-4581-b24b-3b72683ad432
ms.openlocfilehash: 7f2f39ef124220ddee0b42242a9991d63fe5969a
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521257"
---
# <a name="vfscanfs-vfwscanfs"></a>vfscanf_s, vfwscanf_s

Biçimlendirilmiş verileri bir akıştan okur. Bu sürümleri vfscanf, vfwscanf dosyalarının güvenlik geliştirmeleri açıklandığı [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
int vfscanf_s(
   FILE *stream,
   const char *format,
   va_list arglist
);
int vfwscanf_s(
   FILE *stream,
   const wchar_t *format,
   va_list arglist
);
```

### <a name="parameters"></a>Parametreler

*Stream*<br/>
İşaretçi **dosya** yapısı.

*Biçim*<br/>
Biçim denetimi dizesi.

*arglist*<br/>
Değişken bağımsız değişken listesi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, başarıyla dönüştürülen ve atanan alanların sayısını döndürür; dönüş değeri, Okunmuş ancak atanmamış alanları içermez. 0 değeri hiçbir alan atanmamış belirtir. Bir hata oluşursa veya dosya akışı sonuna ilk dönüştürmeden önce ulaşılırsa, dönüş değeri olduğu **EOF** için **vfscanf_s** ve **vfwscanf_s**.

Bu işlevler kendi parametrelerini doğrular. Varsa *stream* bir geçersiz dosya işaretçisiyse veya *biçimi* null bir işaretçiyse, açıklandığı gibi bu işlevler geçersiz parametre işleyicisini çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **EOF** ayarlayıp **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**Vfscanf_s** işlevi, geçerli konumundan verileri okur *stream* tarafından verilen konumlara *arglist* bağımsız değişken listesi (varsa). Listedeki her bağımsız değişken içinde bir tür belirleyiciye karşılık gelen bir tür bir değişken, bir işaretçi olmalıdır *biçimi*. *Biçim* giriş alanlarının yorumunu aynı denetler ve form ve işleve *biçimi* için bağımsız değişken **scanf_s**; bkz [biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md) açıklamasını *biçimi*. **vfwscanf_s** geniş karakterli sürümüdür **vfscanf_s**; biçim bağımsız değişkenler **vfwscanf_s** geniş karakterli bir dizedir. Bu işlevler, akış ANSI modunda açıldığında aynı şekilde davranır. **vfscanf_s** şu anda UNICODE akışından girişi desteklemez.

Daha güvenli işlevler arasındaki temel fark (sahip **_Yanları** soneki) ve diğer sürümleri daha güvenli işlevler her karakter cinsinden boyutu önermesinden **c**, **C**, **s**, **S**, ve **[** türü alanı değişkeni takip bağımsız değişken olarak geçirilecek. Daha fazla bilgi için [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) ve [scanf genişlik belirtimi](../../c-runtime-library/scanf-width-specification.md).

> [!NOTE]
> Boyut parametresi türünde **işaretsiz**değil **size_t**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vftscanf_s**|**vfscanf_s**|**vfscanf_s**|**vfwscanf_s**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**vfscanf_s**|\<stdio.h >|
|**vfwscanf_s**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_vfscanf_s.c
// compile with: /W3
// This program writes formatted
// data to a file. It then uses vfscanf_s to
// read the various data back from the file.

#include <stdio.h>
#include <stdarg.h>
#include <stdlib.h>

FILE *stream;

int call_vfscanf_s(FILE * istream, char * format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vfscanf_s(istream, format, arglist);
    va_end(arglist);
    return result;
}

int main(void)
{
    long l;
    float fp;
    char s[81];
    char c;

    if (fopen_s(&stream, "vfscanf_s.out", "w+") != 0)
    {
        printf("The file vfscanf_s.out was not opened\n");
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
        call_vfscanf_s(stream, "%s %ld %f%c", s, _countof(s), &l, &fp, &c, 1);

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)<br/>
[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[vfscanf, vfwscanf](vfscanf-vfwscanf.md)<br/>
