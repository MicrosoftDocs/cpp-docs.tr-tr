---
title: getchar, getwchar
ms.date: 11/04/2016
apiname:
- getchar
- getwchar
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 5f8d7dbeb35c8818706eb6070df613df8654feb6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626609"
---
# <a name="getchar-getwchar"></a>getchar, getwchar

Standart girişten bir karakter okur.

## <a name="syntax"></a>Sözdizimi

```C
int getchar();
wint_t getwchar();
```

## <a name="return-value"></a>Dönüş Değeri

Okuma karakteri döndürür. Bir okuma hatası ya da dosya sonu koşulu belirtmek üzere **getchar** döndürür **EOF**, ve **getwchar** döndürür **WEOF**. İçin **getchar**, kullanın **ferror** veya **feof** bir hata veya dosya sonunu denetlemek için.

## <a name="remarks"></a>Açıklamalar

Her bir rutin tek bir karakter okur **stdin** ve sonraki karaktere işaret etmek için ilgili dosya işaretleyicisini artırır. **getchar** aynı [_fgetchar](fgetc-fgetwc.md), ancak bir işlev ve makro olarak uygulanır.

Bu işlevler, çağıran iş parçacığının kilitler ve bu nedenle iş parçacığı bakımından güvenlidir. Kilitleme yapılmayan bir sürüm için bkz. [_getchar_nolock, _getwchar_nolock](getchar-nolock-getwchar-nolock.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettchar**|**getchar**|**getchar**|**getwchar**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**getchar**|\<stdio.h >|
|**getwchar**|\<stdio.h > veya \<wchar.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
