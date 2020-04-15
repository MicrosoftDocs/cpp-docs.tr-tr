---
title: getc, getwc
ms.date: 4/2/2020
api_name:
- getwc
- getc
- _o_getc
- _o_getwc
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _gettc
- getwc
- _gettchar
- getc
helpviewer_keywords:
- characters, reading
- _gettc function
- getwchar function
- streams, reading characters from
- reading characters from streams
- getc function
- getwc function
- gettc function
ms.assetid: 354ef514-d0c7-404b-92f5-995f6a834bb3
ms.openlocfilehash: 5c05d7a2743cd0c1e843d6895e8f5574031ab098
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344841"
---
# <a name="getc-getwc"></a>getc, getwc

Bir akışından bir karakter okuyun.

## <a name="syntax"></a>Sözdizimi

```C
int getc(
   FILE *stream
);
wint_t getwc(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
Giriş akışı.

## <a name="return-value"></a>Dönüş Değeri

Okunan karakteri döndürür. Okuma hatası veya dosya sonu koşulu belirtmek için **getc** **EOF**döndürür ve **getwc** **WEOF**döndürür. **getc**için, bir hata veya dosya sonu için kontrol etmek için **ferror** veya **feof** kullanın. *Akış* **NULL**ise, **getc** ve **getwc** geçersiz parametre işleyicisi çağırır, [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi . Yürütme devam etmesine izin verilirse, bu işlevler **EOF** (veya **getwc**için **WEOF)** döndürün ve **EINVAL** **için errno** ayarlayın.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

Her yordam, geçerli konumdaki bir dosyadan tek bir karakter okur ve ilişkili dosya işaretçisini (tanımlanmışsa) bir sonraki karaktere işaret etmek için artışlar. Dosya *akışı*ile ilişkilidir.

Bu işlevler arama iş parçacığı kilitler ve bu nedenle iş parçacığı güvenlidir. Kilitsiz bir sürüm için [_getc_nolock, _getwc_nolock](getc-nolock-getwc-nolock.md)bakın.

Rutine özel açıklamalar takip edin.

|Yordam|Açıklamalar|
|-------------|-------------|
|**getc**|**Fgetc**ile aynı , ama bir işlev ve makro olarak uygulanır.|
|**getwc**|**Getc**geniş karakterli sürümü . *Akış* metin modunda mı yoksa ikili modda mı açıldığına göre çok baytlı bir karakter veya geniş bir karakter okur.|

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettc**|**getc**|**getc**|**getwc**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**getc**|\<stdio.h>|
|**getwc**|\<stdio.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_getc.c
// Use getc to read a line from a file.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;
    FILE* fp;

    // Read a single line from the file "crt_getc.txt".

    fopen_s(&fp, "crt_getc.txt", "r");
    if (!fp)
    {
       printf("Failed to open file crt_getc.txt.\n");
       exit(1);
    }

    for (i = 0; (i < 80) && ((ch = getc(fp)) != EOF)
                         && (ch != '\n'); i++)
    {
        buffer[i] = (char) ch;
    }

    // Terminate string with a null character
    buffer[i] = '\0';
    printf( "Input was: %s\n", buffer);

    fclose(fp);
}
```

### <a name="input-crt_getctxt"></a>Giriş: crt_getc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıktı

```Output
Input was: Line one.
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
