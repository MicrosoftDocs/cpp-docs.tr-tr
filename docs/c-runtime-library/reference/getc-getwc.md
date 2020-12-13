---
description: 'Daha fazla bilgi edinin: getc, getwc'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 0d48b0d1549009d6eb36f37f2f08cb393fde6ecb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338921"
---
# <a name="getc-getwc"></a>getc, getwc

Akıştan bir karakter okur.

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

*ka*<br/>
Giriş akışı.

## <a name="return-value"></a>Dönüş Değeri

Okunan karakteri döndürür. Bir okuma hatası veya dosya sonu koşulu belirtmek için, **getc** **EOF** döndürür ve **getwc** , **weof** döndürür. **Getc** için, bir hatayı denetlemek veya dosya sonu için **ferror** veya **feof** kullanın. *Stream* **null** ise, **getc** ve **getwc** [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **EOF** (veya **getwc** için **weof** ) döndürür ve **errno** , **EINVAL** olarak ayarlanır.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

Her yordam, geçerli konumdaki bir dosyadan tek bir karakteri okur ve ilgili dosya işaretçisini (tanımlanmışsa) sonraki karakteri işaret etmek üzere arttırır. Dosya *akışıyla* ilişkilendirildi.

Bu işlevler çağıran iş parçacığını kilitler ve bu nedenle iş parçacığı güvenlidir. Kilitleme dışı bir sürüm için bkz. [_getc_nolock, _getwc_nolock](getc-nolock-getwc-nolock.md).

Rutin olarak özgü notlar izler.

|Yordam|Açıklamalar|
|-------------|-------------|
|**getc**|**Fgetc** ile aynıdır, ancak bir işlev olarak ve bir makro olarak uygulanır.|
|**getwc**|**Getc**'nin geniş karakterli sürümü. *Akışın* metin modunda veya ikili modda açılıp açılmayacağı için çok baytlı bir karakter veya geniş bir karakter okur.|

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettc**|**getc**|**getc**|**getwc**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**getc**|\<stdio.h>|
|**getwc**|\<stdio.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
