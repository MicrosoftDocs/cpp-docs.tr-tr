---
title: _getche_nolock, _getwche_nolock
description: _Getche_nolock için API başvurusu ve _getwche_nolock; Bu, yankıyı ve iş parçacığını kilitlemeden konsolundan bir karakter alır.
ms.date: 4/2/2020
api_name:
- _getche_nolock
- _getwche_nolock
- _o__getche_nolock
- _o__getwche_nolock
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
- api-ms-win-crt-conio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getche_nolock
- _gettche_nolock
- _getwche_nolock
- getche_nolock
- getwche_nolock
- gettche_nolock
helpviewer_keywords:
- characters, getting from console
- _gettche_nolock function
- getwche_nolock function
- _getche_nolock function
- getche_nolock function
- console, reading from
- _getwche_nolock function
- gettche_nolock function
ms.assetid: 9e853ad4-4d8a-4442-9ae5-da4b434f0b8c
ms.openlocfilehash: faee0ea1e104367a113b5462cb8aa7541646976d
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556078"
---
# <a name="_getche_nolock-_getwche_nolock"></a>_getche_nolock, _getwche_nolock

, Yankıyı ve iş parçacığını kilitlemeden konsolundan bir karakter alır.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _getche_nolock( void );
wint_t _getwche_nolock( void );
```

## <a name="return-value"></a>Dönüş Değeri

Okunan karakteri döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

**_getche_nolock** ve **_getwche_nolock** , **_getche** ve **_getwche** aynıdır, ancak diğer iş parçacıkları tarafından girişim tarafından korunmazlar. Diğer iş parçacıklarını kilitleme yükünü sunmadığından daha hızlı olabilir. Bu işlevleri yalnızca, tek iş parçacıklı uygulamalar gibi iş parçacığı güvenli bağlamlarda veya çağırma kapsamının iş parçacığı yalıtımını zaten işlediği yerde kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_gettche_nolock**|**_getche_nolock**|**_getch_nolock**|**_getwche_nolock**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getche_nolock**|\<conio.h>|
|**_getwche_nolock**|\<conio.h> veya \<wchar.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_getche_nolock.c
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
      ch = _getche_nolock();
      ch = toupper( ch );
   } while( ch != 'Y' );

   _putch_nolock( ch );
   _putch_nolock( '\r' );    // Carriage return
   _putch_nolock( '\n' );    // Line feed
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
