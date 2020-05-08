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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: b01456d3ed37c34dbc10980ebdfbe008e27f624a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913607"
---
# <a name="gets_s-_getws_s"></a>gets_s, _getws_s

**Stdin** akışından bir satır alır. Bu sürümlerinde, [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri [_getws](../../c-runtime-library/gets-getws.md) .

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

*arabelleğin*<br/>
Giriş dizesi için depolama konumu.

*sizeInCharacters*<br/>
Arabelleğin boyutu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa *arabelleği* döndürür. **Null** işaretçisi bir hata veya dosya sonu koşulunu gösterir. Hangi birinin oluştuğunu öğrenmek için [ferror](ferror.md) veya [feof](feof.md) kullanın.

## <a name="remarks"></a>Açıklamalar

**Gets_s** işlevi standart giriş akışı **stdin** öğesinden bir satırı okur ve *arabelleğe*kaydeder. Satır, ilk yeni satır karakteri (' \n ') dahil olmak üzere tüm karakterlerden oluşur. **gets_s** sonra satırı döndürmeden önce yeni satır karakterini null karakter (' \ 0 ') ile değiştirir. Buna karşılık **fgets_s** işlevi yeni satır karakterini korur.

Okunan ilk karakter dosya sonu karakter ise, *arabelleğin* başlangıcında null karakter depolanır ve **null** döndürülür.

**_getws_s** , **gets_s**geniş karakterli bir sürümüdür; bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir.

*Buffer* **null** veya *sizeInCharacters* , sıfıra eşit veya daha küçükse ya da arabellek giriş satırını ve null sonlandırıcıyı içermesi için çok küçük ise, bu işlevler [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklanan şekilde geçersiz bir parametre işleyicisi çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **null** döndürür ve errno, **ERANGE**olarak ayarlanır.

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_getts_s**|**gets_s**|**gets_s**|**_getws_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**gets_s**|\<stdio. h>|
|**_getws_s**|\<stdio. h> veya \<wchar. h>|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout**ve **stderr**Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
