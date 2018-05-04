---
title: _getch, _getwch | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _getch
- _getwch
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
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- getwch
- _getch
- _getwch
dev_langs:
- C++
helpviewer_keywords:
- characters, getting from console
- getch function
- _getwch function
- console, reading from
- _getch function
- getwch function
ms.assetid: cc116be7-cff2-4274-970f-5e7b18ccc05c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b69149340d2fca15071292001b9936e9d3bd5470
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="getch-getwch"></a>_getch, _getwch

Konsolundan Yankı olmadan bir karakteri alır.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _getch( void );
wint_t _getwch( void );
```

## <a name="return-value"></a>Dönüş Değeri

Okuma karakteri döndürür. Döndürülen hata yoktur.

## <a name="remarks"></a>Açıklamalar

**_Getch** ve **_getwch** işlevleri okuma tek bir karakter konsoldan karakter Yankı olmadan. Bu işlevler hiçbiri CTRL + C okumak için kullanılabilir. Bir işlev tuşu veya bir ok tuşu okurken, her işlev iki kez çağrılması gerekir; ilk çağrıda 0 veya 0xE0 döndürür ve ikinci çağrı gerçek anahtar kodu döndürür.

Bu işlevler çağıran iş parçacığı Kilitle ve bu nedenle iş parçacığı güvenlidir. Kilitleme olmayan sürümleri için bkz: [_getch_nolock, _getwch_nolock](getch-nolock-getwch-nolock.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_gettch**|**_getch**|**_getch**|**_getwch**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getch**|\<conio.h >|
|**_getwch**|\<conio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_getch.c
// compile with: /c
// This program reads characters from
// the keyboard until it receives a 'Y' or 'y'.

#include <conio.h>
#include <ctype.h>

int main( void )
{
   int ch;

   _cputs( "Type 'Y' when finished typing keys: " );
   do
   {
      ch = _getch();
      ch = toupper( ch );
   } while( ch != 'Y' );

   _putch( ch );
   _putch( '\r' );    // Carriage return
   _putch( '\n' );    // Line feed
}
```

```Input
abcdefy
```

```Output
Type 'Y' when finished typing keys: Y
```

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_getche, _getwche](getche-getwche.md)<br/>
[_cgets, _cgetws](../../c-runtime-library/cgets-cgetws.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock](ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)<br/>
