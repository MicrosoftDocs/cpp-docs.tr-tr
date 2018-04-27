---
title: vfscanf_s, vfwscanf_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 9b0133f0-9a18-4581-b24b-3b72683ad432
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24f4797cab8b01f45c00c38da31bc2fcf67fc957
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="vfscanfs-vfwscanfs"></a>vfscanf_s, vfwscanf_s

Okuma akışı verilerden biçimlendirilmiş. Bu sürümlerine vfscanf, vfwscanf sahip güvenlik geliştirmeleri açıklandığı gibi [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*Akış*<br/>
İşaretçi **dosya** yapısı.

*Biçimi*<br/>
Biçim denetimi dizesi.

*arglist*<br/>
Değişken bağımsız değişken listesi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri başarıyla dönüştürülür ve atanmış olan alan sayısını döndürür; dönüş değerini okumak ancak atanmamış alanları içermez. Dönüş değeri 0, hiçbir alan atandığını belirtir. Bir hata oluşursa veya dosya akışı sonuna ilk dönüştürmeden önce dönüş değeri **EOF** için **vfscanf_s** ve **vfwscanf_s**.

Bu işlevler kendi parametreleri doğrulayın. Varsa *akış* geçersiz dosya işaretçi veya *biçimi* null işaretçi açıklandığı gibi bu işlevleri geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş **EOF** ve **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**Vfscanf_s** işlevi geçerli konumunu veri okuyan *akış* tarafından verilen konumları içine *arglist* bağımsız değişken listesi (varsa). Listedeki her bir bağımsız değişkeni bir tür belirteci karşılık gelen bir türde bir değişken için bir işaretçi olmalıdır *biçimi*. *Biçim* giriş yorumu alanları ve aynı denetimleri form ve olarak işlev *biçimi* bağımsız değişkeni için **scanf_s**; bkz [biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md) bir açıklaması için *biçimi*. **vfwscanf_s** bir joker karakter sürümü **vfscanf_s**; biçim bağımsız değişkeni **vfwscanf_s** bir joker karakter dizesidir. Akış ANSI modunda açtıysanız bu işlevler aynı şekilde davranır. **vfscanf_s** UNICODE akışı girişten şu anda desteklemiyor.

Daha güvenli işlevleri arasındaki temel fark (sahip **_Yanları** soneki) ve diğer sürümleri daha güvenli işlevleri her karakter cinsinden boyutu gerektirir **c**, **C**, **s**, **S**, ve **[** türü değişkeni hemen ardından bağımsız değişken olarak geçirilen özgüdür. Daha fazla bilgi için bkz: [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) ve [sacnf genişlik belirtimi](../../c-runtime-library/scanf-width-specification.md).

> [!NOTE]
> Boyutu parametresi türünde **imzasız**değil **size_t**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vftscanf_s**|**vfscanf_s**|**vfscanf_s**|**vfwscanf_s**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**vfscanf_s**|\<stdio.h >|
|**vfwscanf_s**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)<br/>
[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[vfscanf, vfwscanf](vfscanf-vfwscanf.md)<br/>
