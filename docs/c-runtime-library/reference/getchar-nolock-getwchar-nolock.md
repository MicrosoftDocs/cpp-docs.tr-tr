---
title: _getchar_nolock, _getwchar_nolock
ms.date: 11/04/2016
api_name:
- _getchar_nolock
- _getwchar_nolock
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
- getwchar_nolock
- _getwchar_nolock
- _getchar_nolock
- getchar_nolock
helpviewer_keywords:
- _getwchar_nolock function
- getwchar_nolock function
- characters, reading
- _getchar_nolock function
- getchar_nolock function
- standard input, reading from
ms.assetid: dc49ba60-0647-4ae9-aa9a-a0618b1666de
ms.openlocfilehash: df7d07d4478d8feee1d5a0b35c40e4158a93be82
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955403"
---
# <a name="_getchar_nolock-_getwchar_nolock"></a>_getchar_nolock, _getwchar_nolock

Standart girişten bir karakter okur.

## <a name="syntax"></a>Sözdizimi

```C
int _getchar_nolock( void );
wint_t _getwchar_nolock( void );
```

## <a name="return-value"></a>Dönüş Değeri

Bkz. [GetChar, getwchar](getchar-getwchar.md).

## <a name="remarks"></a>Açıklamalar

**_getchar_nolock** ve **_getwchar_nolock** , diğer iş parçacıkları tarafından girişime karşı korunmamaları hariç **GetChar** ve **getwchar** ile aynıdır. Diğer iş parçacıklarını kilitleme yükünü sunmadığından daha hızlı olabilir. Bu işlevleri yalnızca, tek iş parçacıklı uygulamalar gibi iş parçacığı güvenli bağlamlarda veya çağırma kapsamının iş parçacığı yalıtımını zaten işlediği yerde kullanın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_gettchar_nolock**|**_getchar_nolock**|**_getchar_nolock**|**_getwchar_nolock**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getchar_nolock**|\<stdio. h >|
|**_getwchar_nolock**|\<stdio. h > veya \<wchar. h >|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout**ve **stderr**Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_getchar_nolock.c
// Use _getchar_nolock to read a line from stdin.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;

    for (i = 0; (i < 80) && ((ch = _getchar_nolock()) != EOF)
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
