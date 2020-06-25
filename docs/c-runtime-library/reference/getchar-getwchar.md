---
title: getchar, getwchar
ms.date: 06/23/2020
api_name:
- getchar
- getwchar
- _o_getchar
- _o_getwchar
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: c6a02f16c3ee3d3e3bc4f86026719a1bd2885416
ms.sourcegitcommit: 8645408c7929558b8162f781776d0908d790a41c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85334977"
---
# <a name="getchar-getwchar"></a>getchar, getwchar

Standart girişten bir karakter okur.

## <a name="syntax"></a>Syntax

```C
int getchar();
wint_t getwchar();
```

## <a name="return-value"></a>Dönüş Değeri

Okunan karakteri döndürür. Bu işlevler giriş için bekler ve giriş kullanılabilir olana kadar geri dönmemelidir.

Bir okuma hatası veya dosya sonu koşulu belirtmek için **GetChar** , **EOF**döndürür ve **getwchar** , **weof**döndürür. **GetChar**için, bir hatayı denetlemek veya dosya sonu için **ferror** veya **feof** kullanın.

## <a name="remarks"></a>Açıklamalar

Her yordam, **stdin** 'den tek bir karakter okur ve bir sonraki karakteri işaret etmek için ilişkili dosya işaretçisini arttırır. **GetChar** [_fgetchar](fgetc-fgetwc.md)aynıdır, ancak bir işlev ve makro olarak uygulanır.

Bu işlevler, çağıran iş parçacığını de kilitler ve iş parçacığı güvenlidir. Kilitleme dışı bir sürüm için bkz. [_getchar_nolock, _getwchar_nolock](getchar-nolock-getwchar-nolock.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettchar**|**GetChar**|**GetChar**|**getwchar**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**GetChar**|\<stdio.h>|
|**getwchar**|\<stdio.h> veya \<wchar.h>|

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

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
