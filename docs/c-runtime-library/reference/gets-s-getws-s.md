---
title: gets_s, _getws_s
ms.date: 4/2/2020
api_name:
- _getws_s
- gets_s
- _o__getws_s
- _o_gets_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: aac64a42a2979623f4314f7bf28d7e4917eaee18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344212"
---
# <a name="gets_s-_getws_s"></a>gets_s, _getws_s

**Stdin** akışından bir çizgi alır. CrT Güvenlik [Özellikleri](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı [gibi, alır, _getws](../../c-runtime-library/gets-getws.md) güvenlik geliştirmeleri var bu sürümleri.

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

*sizeKarakter*<br/>
Arabelleğe in boyutu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa *arabellek* döndürür. **NULL** işaretçisi bir hata veya dosya sonu koşulunu gösterir. Hangisinin oluştuğunu belirlemek için [ferror](ferror.md) veya [feof](feof.md) kullanın.

## <a name="remarks"></a>Açıklamalar

**gets_s** işlevi standart giriş akışı **stdin** bir satır okur ve *arabellek*tepolar. Çizgi, ilk yeni satır karakteri ('\n') dahil olmak üzere tüm karakterlerden oluşur. **gets_s** sonra satırı döndürmeden önce yeni satır karakterini null karakterle ('\0') değiştirir. Buna karşılık, **fgets_s** işlevi yeni satır karakterini korur.

Okunan ilk karakter dosya sonu karakteriyse, *arabellek* başında null bir karakter depolanır ve **NULL** döndürülür.

**_getws_s** **gets_s**geniş karakterli bir versiyonudur; bağımsız değişkeni ve döndürme değeri geniş karakterli dizeleridir.

*Arabellek* **NULL** veya *sizeInCharacters* az veya sıfıra eşit ise veya arabellek giriş satırı ve null sonlandırıcı içerecek kadar küçükise, bu işlevler [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre işleyicisi çağırır. Yürütme devam etmesine izin verilirse, bu işlevler **NULL** döndürün ve **ERANGE**için errno ayarlayın.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkartabilir (boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir) ve eski, güvenli olmayan işlevleri yeni, güvenli karşılıklarıyla otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_getts_s**|**gets_s**|**gets_s**|**_getws_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**gets_s**|\<stdio.h>|
|**_getws_s**|\<stdio.h> \<veya wchar.h>|

Konsol, Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Konsol, **stdin,** **stdout**ve **stderr**ile ilişkili standart akış kolları, C çalışma zamanı işlevleri UWP uygulamalarında bunları kullanamadan önce yönlendirilmelidir. Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
