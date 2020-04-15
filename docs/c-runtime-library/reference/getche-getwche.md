---
title: _getche, _getwche
ms.date: 4/2/2020
api_name:
- _getwche
- _getche
- _o__getche
- _o__getwche
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- getwche
- _getche
- _getwche
helpviewer_keywords:
- characters, getting from console
- _getwche function
- getche function
- console, reading from
- getwche function
- _getche function
ms.assetid: eac978a8-c43a-4130-938f-54f12e2a0fda
ms.openlocfilehash: 59af5360ed8d966629d5e46f77681631a521d502
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344535"
---
# <a name="_getche-_getwche"></a>_getche, _getwche

Yankı ile konsoldan bir karakter alır.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _getche( void );
wint_t _getwche( void );
```

## <a name="return-value"></a>Dönüş Değeri

Okunan karakteri döndürür. Hata iadesi yok.

## <a name="remarks"></a>Açıklamalar

**_getche** ve **_getwche** işlevleri, konsoldan yankı ile tek bir karakter okur, yani karakter konsolda görüntülenir. Bu işlevlerin hiçbiri CTRL+C okumak için kullanılamaz. Bir işlev tuşu veya ok tuşu okurken, her işlev iki kez çağrılmalıdır; ilk arama 0 veya 0xE0 döndürür ve ikinci arama gerçek anahtar kodunu döndürür.

Bu işlevler arama iş parçacığı kilitler ve bu nedenle iş parçacığı güvenlidir. Kilitlenmeyen sürümler için [bkz. _getche_nolock, _getwche_nolock.](getche-nolock-getwche-nolock.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_getche**|**_getche**|**_getch**|**_getwche**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getche**|\<conio.h>|
|**_getwche**|\<conio.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Konsol ve Bağlantı Noktası G/Ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cgets, _cgetws](../../c-runtime-library/cgets-cgetws.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock](ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)<br/>
