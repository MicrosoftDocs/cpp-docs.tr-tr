---
title: gets, _getws
ms.date: 4/2/2020
api_name:
- _getws
- gets
- _o__getws
- _o_gets
api_location:
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getts
- gets
- _getws
helpviewer_keywords:
- getws function
- getts function
- _getws function
- lines, getting
- streams, getting lines
- _getts function
- gets function
- standard input, reading from
ms.assetid: 1ec2dd4b-f801-48ea-97c2-892590f16024
ms.openlocfilehash: a1fd3218f75079554d049d4ef4c3691a2fbdd542
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349326"
---
# <a name="gets-_getws"></a>gets, _getws

`stdin` Akıştan bir satır alır. Bu işlevlerin daha güvenli sürümleri mevcuttur; [gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md)bakın.

> [!IMPORTANT]
> Bu işlevler geçersizdir. Visual Studio 2015'ten itibaren CRT'de kullanılamazlar. Bu işlevlerin güvenli sürümleri, gets_s ve _getws_s, hala kullanılabilir. Bu alternatif işlevler hakkında daha fazla bilgi için [gets_s, _getws_s.](../c-runtime-library/reference/gets-s-getws-s.md)

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```
char *gets(
   char *buffer
);
wchar_t *_getws(
   wchar_t *buffer
);
template <size_t size>
char *gets(
   char (&buffer)[size]
); // C++ only
template <size_t size>
wchar_t *_getws(
   wchar_t (&buffer)[size]
); // C++ only
```

#### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Giriş dizesi için depolama konumu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa bağımsız değişkenini döndürür. **NULL** işaretçisi bir hata veya dosya sonu koşulunu gösterir. Hangisinin oluştuğunu belirlemek için [ferror](../c-runtime-library/reference/ferror.md) veya [feof](../c-runtime-library/reference/feof.md) kullanın. NULL `buffer` **NULL**ise, bu işlevler [Parametre Doğrulama](../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre işleyicisi çağırır. Yürütmedevam etmesine izin verilirse, **NULL** bu işlevler NULL `EINVAL`döndürdü ve errno'ya ayarlar.

## <a name="remarks"></a>Açıklamalar

İşlev, `gets` standart giriş akışından `stdin` bir satır `buffer`okur ve onu . Çizgi, ilk yeni satır karakteri ('\n') dahil olmak üzere tüm karakterlerden oluşur. `gets`sonra satırı döndürmeden önce yeni satır karakterini null karakteri ('\0') ile değiştirir. Buna karşılık, `fgets` işlev yeni çizgi karakterini korur. `_getws`geniş karakterli bir `gets`versiyonudur; bağımsız değişkeni ve döndürme değeri geniş karakterli dizeleridir.

> [!IMPORTANT]
> Gets tarafından okunan karakter sayısını sınırlamanın bir yolu olmadığından, güvenilmeyen giriş arabellek taşmaları kolayca neden olabilir. Bunun yerine `fgets` kullanın.

C++'da, bu işlevlerin daha yeni ve güvenli karşıtlarını çağıran şablon aşırı yüklemeleri vardır. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_getts`|`gets`|`gets`|`_getws`|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`gets`|\<stdio.h>|
|`_getws`|\<stdio.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```c
// crt_gets.c
// compile with: /WX /W3

#include <stdio.h>

int main( void )
{
   char line[21]; // room for 20 chars + '\0'
   gets( line );  // C4996
   // Danger: No way to limit input to 20 chars.
   // Consider using gets_s instead.
   printf( "The line entered was: %s\n", line );
}
```

20 karakterden uzun girişin satır arabelleği aşındıracağını ve neredeyse kesinlikle programın çökmesine neden olacağını unutmayın.

```Output

Hello there!The line entered was: Hello there!
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../c-runtime-library/stream-i-o.md)<br/>
[fgets, fgetws](../c-runtime-library/reference/fgets-fgetws.md)<br/>
[fputs, fputws](../c-runtime-library/reference/fputs-fputws.md)<br/>
[puts, _putws](../c-runtime-library/reference/puts-putws.md)
