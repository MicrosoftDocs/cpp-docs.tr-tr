---
title: _getch_nolock, _getwch_nolock
ms.date: 11/04/2016
api_name:
- _getwch_nolock
- _getch_nolock
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
ms.openlocfilehash: 9c8f27b468d0471f44211efa12dcee6453b3fac1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955462"
---
# <a name="_getch_nolock-_getwch_nolock"></a>_getch_nolock, _getwch_nolock

, Yankısız ve iş parçacığını kilitlemeden konsoldan bir karakter alır.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _getch_nolock( void );
wint_t _getwch_nolock( void );
```

## <a name="return-value"></a>Dönüş Değeri

Okunan karakteri döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

**_getch_nolock** ve **_getwch_nolock** , diğer iş parçacıkları tarafından girişime karşı korumamaları hariç **_getch** ve **_getchw** ile özdeştir. Diğer iş parçacıklarını kilitleme yükünü sunmadığından daha hızlı olabilir. Bu işlevleri yalnızca, tek iş parçacıklı uygulamalar gibi iş parçacığı güvenli bağlamlarda veya çağırma kapsamının iş parçacığı yalıtımını zaten işlediği yerde kullanın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_gettch_nolock**|**_getch_nolock**|**_getch_nolock**|**_getwch_nolock**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getch_nolock**|\<conio. h >|
|**_getwch_nolock**|\<conio. h > veya \<wchar. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_getche, _getwche](getche-getwche.md)<br/>
[_cgets, _cgetws](../../c-runtime-library/cgets-cgetws.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock](ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)<br/>
