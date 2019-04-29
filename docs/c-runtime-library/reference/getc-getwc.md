---
title: getc, getwc
ms.date: 11/04/2016
apiname:
- getwc
- getc
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
ms.openlocfilehash: bbaee79eac6802959a11f7f1ba30eaf590ecf2f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331876"
---
# <a name="getc-getwc"></a>getc, getwc

Bir karakter, bir akıştan okuyun.

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

*Stream*<br/>
Giriş akışı.

## <a name="return-value"></a>Dönüş Değeri

Okuma karakteri döndürür. Bir okuma hatası ya da dosya sonu koşulu belirtmek üzere **getc** döndürür **EOF**, ve **getwc** döndürür **WEOF**. İçin **getc**, kullanın **ferror** veya **feof** bir hata veya dosya sonunu denetlemek için. Varsa *stream* olduğu **NULL**, **getc** ve **getwc** açıklandığı gibi geçersiz parametre işleyicisini çağırır [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **EOF** (veya **WEOF** için **getwc**) ayarlayıp **errno** için  **EINVAL**.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

Her bir rutin tek bir karakter bir dosyadan geçerli konumu ve artışlarla ilgili dosya işaretleyicisini (tanımlıysa) sonraki karaktere işaret edecek şekilde okur. İle ilişkili dosya *stream*.

Bu işlevler, çağıran iş parçacığının kilitler ve bu nedenle iş parçacığı bakımından güvenlidir. Kilitleme yapılmayan bir sürüm için bkz. [_getc_nolock, _getwc_nolock](getc-nolock-getwc-nolock.md).

Ardından yordama özel açıklamalar gelir.

|Yordam|Açıklamalar|
|-------------|-------------|
|**getc**|Aynı **fgetc**, ancak uygulanan bir işlev ve makro olarak.|
|**getwc**|Geniş karakter sürümünü **getc**. Çok baytlı bir karakter veya geniş bir karakter olup olmadığına göre okur *stream* metin modunda veya İkili modda açılmış.|

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettc**|**getc**|**getc**|**getwc**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**getc**|\<stdio.h >|
|**getwc**|\<stdio.h > veya \<wchar.h >|

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

### <a name="input-crtgetctxt"></a>Giriş: crt_getc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıkış

```Output
Input was: Line one.
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
