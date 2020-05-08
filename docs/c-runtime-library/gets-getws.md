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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 1c60cf14334a0dcc0492b23da10a36c3219bb699
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919907"
---
# <a name="gets-_getws"></a>gets, _getws

`stdin` Akıştan bir satır alır. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md).

> [!IMPORTANT]
> Bu işlevler artık kullanılmıyor. Visual Studio 2015 ' den başlayarak, bu dosyalar CRT içinde kullanılamaz. Bu işlevlerin güvenli sürümleri, gets_s ve _getws_s hala kullanılabilir. Bu alternatif işlevler hakkında daha fazla bilgi için bkz. [gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md).

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*arabelleğin*<br/>
Giriş dizesi için depolama konumu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa bağımsız değişkenini döndürür. **Null** işaretçisi bir hata veya dosya sonu koşulunu gösterir. Hangi birinin oluştuğunu öğrenmek için [ferror](../c-runtime-library/reference/ferror.md) veya [feof](../c-runtime-library/reference/feof.md) kullanın. NULL `buffer` ise **NULL**, bu işlevler [parametre doğrulama](../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **null** döndürür ve errno öğesini olarak `EINVAL`ayarlar.

## <a name="remarks"></a>Açıklamalar

`gets` İşlevi standart giriş akışından `stdin` bir satırı okur ve içinde `buffer`depolar. Satır, ilk yeni satır karakteri (' \n ') dahil olmak üzere tüm karakterlerden oluşur. `gets`sonra satırı döndürmeden önce yeni satır karakterini null karakteri (' \ 0 ') ile değiştirir. Buna karşılık `fgets` işlev, yeni satır karakterini korur. `_getws`, öğesinin `gets`geniş karakterli bir sürümüdür; bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir.

> [!IMPORTANT]
> Tarafından okunan karakter sayısını sınırlamanın bir yolu olmadığından, güvenilmeyen giriş, arabellek taşmalarına kolayca neden olabilir. Bunun yerine `fgets` kullanın.

C++ ' da, bu işlevlerin, bu işlevlerin daha yeni ve güvenli bir şekilde çağrılmasını sağlayan şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_getts`|`gets`|`gets`|`_getws`|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`gets`|\<stdio. h>|
|`_getws`|\<stdio. h> veya \<wchar. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

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

20 karakterden uzun girişlerin satır arabelleğini taşıyacağını ve neredeyse tamamen programın kilitlenmesine neden olduğunu unutmayın.

```Output

Hello there!The line entered was: Hello there!
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../c-runtime-library/stream-i-o.md)<br/>
[fgets, fgetws](../c-runtime-library/reference/fgets-fgetws.md)<br/>
[fputs, fputws](../c-runtime-library/reference/fputs-fputws.md)<br/>
[puts, _putws](../c-runtime-library/reference/puts-putws.md)
