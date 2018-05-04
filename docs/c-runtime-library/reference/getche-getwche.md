---
title: _getche, _getwche | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _getwche
- _getche
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
- getwche
- _getche
- _getwche
dev_langs:
- C++
helpviewer_keywords:
- characters, getting from console
- _getwche function
- getche function
- console, reading from
- getwche function
- _getche function
ms.assetid: eac978a8-c43a-4130-938f-54f12e2a0fda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3afca6d897f1cc8b1cd724b03ca57e3096829b9d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="getche-getwche"></a>_getche, _getwche

Bir karakter Yankı konsoluyla alır.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _getche( void );
wint_t _getwche( void );
```

## <a name="return-value"></a>Dönüş Değeri

Okuma karakteri döndürür. Döndürülen hata yoktur.

## <a name="remarks"></a>Açıklamalar

**_Getche** ve **_getwche** işlevleri konsolundan karakter konsolda görüntülenir anlamına Yankı ile tek bir karakter okuyun. Bu işlevler hiçbiri CTRL + C okumak için kullanılabilir. Bir işlev tuşu veya bir ok tuşu okurken, her işlev iki kez çağrılması gerekir; ilk çağrıda 0 veya 0xE0 döndürür ve ikinci çağrı gerçek anahtar kodu döndürür.

Bu işlevler çağıran iş parçacığı Kilitle ve bu nedenle iş parçacığı güvenlidir. Kilitleme olmayan sürümleri için bkz: [_getche_nolock, _getwche_nolock](getche-nolock-getwche-nolock.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_getche**|**_getche**|**_getch**|**_getwche**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getche**|\<conio.h >|
|**_getwche**|\<conio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_getche.c
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
      ch = _getche();
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
Type 'Y' when finished typing keys: abcdefyY
```

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cgets, _cgetws](../../c-runtime-library/cgets-cgetws.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock](ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)<br/>
