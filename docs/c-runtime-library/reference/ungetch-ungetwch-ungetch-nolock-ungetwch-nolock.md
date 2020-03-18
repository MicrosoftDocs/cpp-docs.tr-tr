---
title: _ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock
ms.date: 11/04/2016
api_name:
- _ungetch_nolock
- _ungetwch_nolock
- _ungetwch
- _ungetch
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
- _ungetch_nolock
- ungetwch
- ungetch_nolock
- _ungetwch
- ungetwch_nolock
- _ungetch
- _ungettch_nolock
- _ungettch
- _ungetwch_nolock
helpviewer_keywords:
- _ungetch function
- ungetwch function
- characters, pushing back to console
- _ungettch_nolock function
- ungettch function
- _ungettch function
- ungetch_nolock function
- ungettch_nolock function
- _ungetwch_nolock function
- _ungetch_nolock function
- ungetwch_nolock function
- _ungetwch function
ms.assetid: 70ae71c6-228c-4883-a57d-de6d5f873825
ms.openlocfilehash: 5fd34d0c975ee49bce688cd902a6df856b5d6963
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443752"
---
# <a name="_ungetch-_ungetwch-_ungetch_nolock-_ungetwch_nolock"></a>_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock

Konsolundan okunan son karakteri geri gönderir.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _ungetch(
   int c
);
wint_t _ungetwch(
   wint_t c
);
int _ungetch_nolock(
   int c
);
wint_t _ungetwch_nolock(
   wint_t c
);
```

### <a name="parameters"></a>Parametreler

*,*<br/>
Gönderilecek karakter.

## <a name="return-value"></a>Dönüş Değeri

Her iki işlev de başarılı olursa *c* karakterini döndürür. Bir hata varsa, **_Ungetch** **EOF** değerini döndürür ve **_ungetwch** **weof**döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevler *c* karakterini konsola geri göndererek, **_getch** veya **_getche** (veya **_getwch** ya da **_getwche**) tarafından okunan bir sonraki karakter *olmasına neden olur* . **_ungetch** ve **_ungetwch** bir sonraki okumadan önce birden çok kez çağrıldıklarında başarısız olur. *C* bağımsız değişkeni **EOF** (veya **weof**) olmayabilir.

**_Nolock** sonekine sahip sürümler, diğer iş parçacıkları tarafından girişime karşı korunmamaları dışında aynıdır. Diğer iş parçacıklarını kilitleyen ek yüke neden olmadıklarından bu, daha hızlı olabilir. Bu işlevleri yalnızca, tek iş parçacıklı uygulamalar gibi iş parçacığı güvenli bağlamlarda veya çağırma kapsamının iş parçacığı yalıtımını zaten işlediği yerde kullanın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettch**|**_ungetch**|**_ungetch**|**_ungetwch**|
|**_ungettch_nolock**|**_ungetch_nolock**|**_ungetch_nolock**|**_ungetwch_nolock**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ungetch**, **_ungetch_nolock**|\<conio. h >|
|**_ungetwch**, **_ungetwch_nolock**|\<conio. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_ungetch.c
// compile with: /c
// In this program, a white-space delimited
// token is read from the keyboard. When the program
// encounters a delimiter, it uses _ungetch to replace
// the character in the keyboard buffer.
//

#include <conio.h>
#include <ctype.h>
#include <stdio.h>

int main( void )
{
   char buffer[100];
   int count = 0;
   int ch;

   ch = _getche();
   while( isspace( ch ) )      // Skip preceding white space.
      ch = _getche();
   while( count < 99 )         // Gather token.
   {
      if( isspace( ch ) )      // End of token.
         break;
      buffer[count++] = (char)ch;
      ch = _getche();
   }
   _ungetch( ch );            // Put back delimiter.
   buffer[count] = '\0';      // Null terminate the token.
   printf( "\ntoken = %s\n", buffer );
}
```

```Output

Whitetoken = White
```

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
