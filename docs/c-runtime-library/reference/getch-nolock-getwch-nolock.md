---
title: _getch_nolock, _getwch_nolock
ms.date: 4/2/2020
api_name:
- _getwch_nolock
- _getch_nolock
- _o__getch_nolock
- _o__getwch_nolock
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
- _getch_nolock
- getwch_nolock
- getch_nolock
- _getwch_nolock
- _gettch_nolock
- gettch_nolock
helpviewer_keywords:
- characters, getting from console
- _getwch_nolock function
- _getch_nolock function
- getwch_nolock function
- _gettch_nolock function
- console, reading from
- getch_nolock function
- gettch_nolock function
ms.assetid: 9d248546-26ca-482c-b0c6-55812a987e83
ms.openlocfilehash: 4ba88ad86b6db892a581b9d94cb36f5ab8240c10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344704"
---
# <a name="_getch_nolock-_getwch_nolock"></a>_getch_nolock, _getwch_nolock

Yankı olmadan ve iş parçacığı kilitleme olmadan konsoldan bir karakter alır.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _getch_nolock( void );
wint_t _getwch_nolock( void );
```

## <a name="return-value"></a>Dönüş Değeri

Okunan karakteri döndürür. Hata iadesi yok.

## <a name="remarks"></a>Açıklamalar

**_getch_nolock** ve **_getwch_nolock,** diğer iş parçacıklarıtarafından karışmadan korunmayan lar dışında **_getch** ve **_getchw** ile aynıdır. Diğer iş parçacığı kilitleme yükü ne olursa olsun onlar daha hızlı olabilir. Bu işlevleri yalnızca tek iş parçacığı uygulamaları gibi iş parçacığı güvenli bağlamlarda veya arama kapsamının iş parçacığı yalıtımını zaten işlediği durumlarda kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_gettch_nolock**|**_getch_nolock**|**_getch_nolock**|**_getwch_nolock**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getch_nolock**|\<conio.h>|
|**_getwch_nolock**|\<conio.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_getch_nolock.c
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
      ch = _getch_nolock();
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
Type 'Y' when finished typing keys: Y
```

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve Bağlantı Noktası G/Ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_getche, _getwche](getche-getwche.md)<br/>
[_cgets, _cgetws](../../c-runtime-library/cgets-cgetws.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock](ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)<br/>
