---
title: gets_s, _getws_s
ms.date: 11/04/2016
apiname:
- _getws_s
- gets_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getws_s
- gets_s
helpviewer_keywords:
- getws_s function
- _getws_s function
- lines, getting
- streams, getting lines
- buffers, avoiding overruns
- buffer overruns
- buffers, buffer overruns
- gets_s function
- standard input, reading from
ms.assetid: 5880c36f-122c-4061-a1a5-aeeced6fe58c
ms.openlocfilehash: f71fafceaf1974bc5ff736ff175a67cf6c924ee6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157662"
---
# <a name="getss-getwss"></a>gets_s, _getws_s

Bir hat alır **stdin** akış. Bu sürümleri [alır, _getws](../../c-runtime-library/gets-getws.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
char *gets_s(
   char *buffer,
   size_t sizeInCharacters
);
wchar_t *_getws_s(
   wchar_t *buffer,
   size_t sizeInCharacters
);
```

```cpp
template <size_t size>
char *gets_s( char (&buffer)[size] ); // C++ only

template <size_t size>
wchar_t *_getws_s( wchar_t (&buffer)[size] ); // C++ only
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Giriş dizesi için depolama konumu.

*sizeInCharacters*<br/>
Arabellek boyutu.

## <a name="return-value"></a>Dönüş Değeri

Döndürür *arabellek* başarılı olursa. A **NULL** işaretçi bir hata veya dosya sonu koşulunu gösterir. Kullanım [ferror](ferror.md) veya [feof](feof.md) hangisinin gerçekleştiğini belirlemek için.

## <a name="remarks"></a>Açıklamalar

**Gets_s** işlevi standart giriş akışından bir satır okur **stdin** ve depolar *arabellek*. En fazla ve ilk yeni satır karakteri ('\n') dahil olmak üzere tüm karakterleri satırın oluşur. **gets_s** daha sonra satırı döndürmeden önce yeni satır karakterini bir null karakteri ('\0') ile değiştirir. Buna karşılık, **fgets_s** işlevi yeni satır karakterini korur.

İlk karakter okuma dosya sonu karakter değilse, bir null karakter başında depolanan *arabellek* ve **NULL** döndürülür.

**_getws_s** geniş karakterli sürümüdür **gets_s**; bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir.

Varsa *arabellek* olduğu **NULL** veya *sizeInCharacters* sıfırdan küçük veya ona eşit veya arabellek null Sonlandırıcı ve giriş satırı içerecek şekilde depolayamayacak kadar küçükse, bu işlevler çağırma bölümünde anlatıldığı gibi geçersiz parametre işleyicisini, [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **NULL** ve errno öğesini **ERANGE**.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kalkar) ve bunlar otomatik olarak eski ve güvenli olmayan işlevlerle daha yeni ve güvenli karşılıklarını değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_getts_s**|**gets_s**|**gets_s**|**_getws_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**gets_s**|\<stdio.h >|
|**_getws_s**|\<stdio.h > veya \<wchar.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_gets_s.c
// This program retrieves a string from the stdin and
// prints the same string to the console.

#include <stdio.h>

int main( void )
{
   char line[21]; // room for 20 chars + '\0'
   gets_s( line, 20 );
   printf( "The line entered was: %s\n", line );
}
```

```Input
Hello there!
```

```Output
The line entered was: Hello there!
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
