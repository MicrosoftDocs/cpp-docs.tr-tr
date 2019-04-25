---
title: gets, _getws
ms.date: 11/04/2016
apiname:
- _getws
- gets
apilocation:
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: bd5f4e885c0291be963320610942415fc7b61172
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62289565"
---
# <a name="gets-getws"></a>gets, _getws

Bir hat alır `stdin` akış. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md).

> [!IMPORTANT]
>  Bu işlevler kullanım dışıdır. Visual Studio 2015'te başlayarak, CRT içinde kullanılamaz. Bu işlevler, gets_s ve _getws_s, güvenli sürümleri yine de kullanılabilir. Bu diğer işlevler hakkında daha fazla bilgi için bkz: [gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md).

> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

Başarılıysa bağımsız değişkenini döndürür. A **NULL** işaretçi bir hata veya dosya sonu koşulunu gösterir. Kullanım [ferror](../c-runtime-library/reference/ferror.md) veya [feof](../c-runtime-library/reference/feof.md) hangisinin gerçekleştiğini belirlemek için. Varsa `buffer` olduğu **NULL**, bu işlevler içinde açıklanan şekilde geçersiz parametre işleyicisini çağırır [Parameter Validation](../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **NULL** ve errno öğesini `EINVAL`.

## <a name="remarks"></a>Açıklamalar

`gets` İşlevi standart giriş akışından bir satır okur `stdin` ve depolar `buffer`. En fazla ve ilk yeni satır karakteri ('\n') dahil olmak üzere tüm karakterleri satırın oluşur. `gets` Daha sonra satırı döndürmeden önce yeni satır karakterini bir null karakteri ('\0') ile değiştirir. Buna karşılık, `fgets` işlevi yeni satır karakterini korur. `_getws` geniş karakterli sürümüdür `gets`; bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir.

> [!IMPORTANT]
>  Alınanlar tarafından okunan karakter sayısını sınırlama yolu yoktur çünkü, güvenilmeyen girişler arabellek taşmalarına kolayca neden olabilir. Bunun yerine `fgets` kullanın.

C++'da, bu işlevler, bu işlevlerin daha yeni ve güvenli karşılıklarını çağırma şablon aşırı yüklemeleri vardır. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_getts`|`gets`|`gets`|`_getws`|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`gets`|\<stdio.h >|
|`_getws`|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```
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

20 karakter girişlerin satır arabelleğini taşırdığını ve neredeyse kesindir programın çökmesine neden daha uzun girişi unutmayın.

```Output

Hello there!The line entered was: Hello there!
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../c-runtime-library/stream-i-o.md)<br/>
[fgets, fgetws](../c-runtime-library/reference/fgets-fgetws.md)<br/>
[fputs, fputws](../c-runtime-library/reference/fputs-fputws.md)<br/>
[puts, _putws](../c-runtime-library/reference/puts-putws.md)
