---
description: 'Hakkında daha fazla bilgi edinin: _getc_nolock _getwc_nolock'
title: _getc_nolock, _getwc_nolock
ms.date: 4/2/2020
api_name:
- _getc_nolock
- _getwc_nolock
- _o__getc_nolock
- _o__getwc_nolock
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
- getc_nolock
- _gettc_nolock
- _getc_nolock
- getwc_nolock
- gettc_nolock
- _getwc_nolock
helpviewer_keywords:
- characters, reading
- _getc_nolock function
- _getwc_nolock function
- getwc_nolock function
- streams, reading characters from
- reading characters from streams
- getc_nolock function
- gettc_nolock function
- _gettc_nolock function
ms.assetid: eb37b272-e177-41c9-b077-12ce7ffd3b88
ms.openlocfilehash: bd09abf0797a1a2c3590a89fcfcd313a443577d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338909"
---
# <a name="_getc_nolock-_getwc_nolock"></a>_getc_nolock, _getwc_nolock

Akıştan bir karakter okur.

## <a name="syntax"></a>Sözdizimi

```C
int _getc_nolock(
   FILE *stream
);
wint_t _getwc_nolock(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
Giriş akışı.

## <a name="return-value"></a>Dönüş Değeri

Bkz. [getc, getwc](getc-getwc.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevler, çağıran iş parçacığını kilitlemeyin hariç **getc** ve **getwc** ile aynıdır. Diğer iş parçacıklarını kilitleme yükünü sunmadığından daha hızlı olabilir. Bu işlevleri yalnızca, tek iş parçacıklı uygulamalar gibi iş parçacığı güvenli bağlamlarda veya çağırma kapsamının iş parçacığı yalıtımını zaten işlediği yerde kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_gettc_nolock**|**getc_nolock**|**getc_nolock**|**getwc_nolock**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**getc_nolock**|\<stdio.h>|
|**getwc_nolock**|\<stdio.h> veya \<wchar.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_getc_nolock.c
// Use getc to read a line from a file.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;
    FILE* fp;

    // Read a single line from the file "crt_getc_nolock.txt".
    fopen_s(&fp, "crt_getc_nolock.txt", "r");
    if (!fp)
    {
       printf("Failed to open file crt_getc_nolock.txt.\n");
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

### <a name="input-crt_getc_nolocktxt"></a>Giriş: crt_getc_nolock.txt

```Input
Line the first.
Line the second.
```

### <a name="output"></a>Çıktı

```Output
Input was: Line the first.
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
