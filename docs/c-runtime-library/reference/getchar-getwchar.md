---
title: getchar, getwchar
ms.date: 11/04/2016
api_name:
- getchar
- getwchar
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- getwchar
- GetChar
helpviewer_keywords:
- gettchar function
- characters, reading
- getwchar function
- _gettchar function
- standard input, reading from
ms.assetid: 19fda588-3e33-415c-bb60-dd73c028086a
ms.openlocfilehash: b969dc48e949efa02b807ec0ea442da7cb793e15
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955410"
---
# <a name="getchar-getwchar"></a>getchar, getwchar

Standart girişten bir karakter okur.

## <a name="syntax"></a>Sözdizimi

```C
int getchar();
wint_t getwchar();
```

## <a name="return-value"></a>Dönüş Değeri

Okunan karakteri döndürür. Bir okuma hatası veya dosya sonu koşulu belirtmek için **GetChar** , **EOF**döndürür ve **getwchar** , **weof**döndürür. **GetChar**için, bir hatayı denetlemek veya dosya sonu için **ferror** veya **feof** kullanın.

## <a name="remarks"></a>Açıklamalar

Her yordam, **stdin** 'den tek bir karakter okur ve bir sonraki karakteri işaret etmek için ilişkili dosya işaretçisini arttırır. **GetChar** , [_fgetchar](fgetc-fgetwc.md)ile aynıdır, ancak bir işlev ve makro olarak uygulanır.

Bu işlevler çağıran iş parçacığını kilitler ve bu nedenle iş parçacığı güvenlidir. Kilitleme dışı bir sürüm için bkz. [_getchar_nolock, _getwchar_nolock](getchar-nolock-getwchar-nolock.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettchar**|**GetChar**|**GetChar**|**getwchar**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**GetChar**|\<stdio. h >|
|**getwchar**|\<stdio. h > veya \<wchar. h >|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout**ve **stderr**Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_getchar.c
// Use getchar to read a line from stdin.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;

    for (i = 0; (i < 80) && ((ch = getchar()) != EOF)
                         && (ch != '\n'); i++)
    {
        buffer[i] = (char) ch;
    }

    // Terminate string with a null character
    buffer[i] = '\0';
    printf( "Input was: %s\n", buffer);
}
```

```Output

This textInput was: This text
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
