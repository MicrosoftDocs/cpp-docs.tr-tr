---
title: fgets, fgetws | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fgets
- fgetws
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
- _fgetts
- fgetws
- fgets
dev_langs:
- C++
helpviewer_keywords:
- _fgetts function
- streams, getting strings from
- streams, reading from
- fgets function
- fgetws function
- fgetts function
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c155150a364c2cbbd230c56678e6e7dcb4e4fde
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027173"
---
# <a name="fgets-fgetws"></a>fgets, fgetws

Bir dize bir akıştan alın.

## <a name="syntax"></a>Sözdizimi

```C
char *fgets(
   char *str,
   int numChars,
   FILE *stream
);
wchar_t *fgetws(
   wchar_t *str,
   int numChars,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Veri için depolama konumu.

*numChars*<br/>
Okunacak karakter sayısı.

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri döndürür *str*. **NULL** bir hata veya dosya sonu koşulu belirtmek için döndürülür. Kullanım **feof** veya **ferror** hata oluşup oluşmadığını belirlemek için. Varsa *str* veya *stream* null bir işaretçiyse veya *numChars* küçük veya ona eşit sıfır olarak açıklandığı gibi bu işlev geçersiz parametre işleyicisi çağırır [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **NULL**.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

**Fgets** işlevi bir dize girdiden okur *stream* bağımsız değişken ve depolar *str*. **fgets** geçerli stream konuma ve akışı sonuna ilk yeni satır karakteri dahil olmak üzere karakterler okur ya da karakter sayısı okunana kadar eşittir *numChars* - 1, hangisinin önce geldiğine bağlı. Sonuç depolanan *str* null karakteri ile eklenir. Yeni satır karakteri, okuma, dizede dahildir.

**fgetws** geniş karakterli sürümüdür **fgets**.

**fgetws** geniş karakter bağımsız değişkeni okur *str* bir çok baytlı karakter veya olup olmadığına göre bir geniş karakterli dize olarak *stream* metin modunda veya İkili modda açılmış sırasıyla. Metin ve ikili modlarda Unicode ve çok baytlı akış g/Ç kullanma hakkında daha fazla bilgi için bkz. [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [metin ve ikili modlarda Unicode Stream g/ç](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgetts**|**fgets**|**fgets**|**fgetws**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fgets**|\<stdio.h >|
|**fgetws**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fgets.c
// This program uses fgets to display 
// the first line from a file.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char line[100];

   if( fopen_s( &stream, "crt_fgets.txt", "r" ) == 0 )
   {
      if( fgets( line, 100, stream ) == NULL)
         printf( "fgets error\numChars" );
      else
         printf( "%s", line);
      fclose( stream );
   }
}
```

### <a name="input-crtfgetstxt"></a>Giriş: crt_fgets.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıkış

```Output
Line one.
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
