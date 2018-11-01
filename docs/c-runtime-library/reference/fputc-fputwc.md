---
title: fputc, fputwc
ms.date: 11/04/2016
apiname:
- fputc
- fputwc
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
- fputc
- fputwc
- _fputtc
helpviewer_keywords:
- streams, writing characters to
- fputtc function
- _fputtc function
- fputwc function
- fputc function
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
ms.openlocfilehash: fc06c9f2060baae63071339768cef11fc5f34023
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447183"
---
# <a name="fputc-fputwc"></a>fputc, fputwc

Bir akışa bir karakter yazar.

## <a name="syntax"></a>Sözdizimi

```C
int fputc(
   int c,
   FILE *stream
);
wint_t fputwc(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Yazılacak karakter.

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri yazılan karakteri döndürür. İçin **fputc**, dönüş değeri **EOF** bir hata olduğunu gösterir. İçin **fputwc**, dönüş değeri **WEOF** bir hata olduğunu gösterir. Varsa *stream* olduğu **NULL**, açıklandığı gibi bu işlevler geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bunlar döndürür **EOF** ayarlayıp **errno** için **EINVAL**.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri tek bir karakter Yazar *c* konumdaki dosyaya belirtilen ilişkili dosya konumu göstergesi (tanımlanmışsa) ve göstergeyi uygun şekilde ilerletir. Durumunda, **fputc** ve **fputwc**, dosyanın ilişkilendirildiği *stream*. Dosya konumlandırma isteği destekleyemiyorsa veya içinde açıldı ekleme modunda açıldıysa, karakter akışın sonuna eklenir.

Akış ANSI modunda açılırsa iki işlev aynı şekilde davranır. **fputc** UNICODE akışına çıkış şu anda desteklemiyor.

Sürümlerle **_nolock** soneki, bunlar başka iş parçacıklarının engellemelerinden korunmamaları hariç, aynıdır. Daha fazla bilgi için[_fputc_nolock, _fputwc_nolock](fputc-nolock-fputwc-nolock.md).

Ardından yordama özel açıklamalar gelir.

|Yordam|Açıklamalar|
|-------------|-------------|
|**fputc**|Eşdeğer **putc**, ancak bir işlev ve makro olarak değil, yalnızca işlev olarak uygulanır.|
|**fputwc**|Geniş karakter sürümünü **fputc**. Yazar *c* bir çok baytlı karakter veya geniş bir karakter olup olmadığına göre *stream* metin modunda veya İkili modda açılmış.|

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputtc**|**fputc**|**fputc**|**fputwc**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fputc**|\<stdio.h >|
|**fputwc**|\<stdio.h > veya \<wchar.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri —**stdin**, **stdout**, ve **stderr**— C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fputc.c
// This program uses fputc
// to send a character array to stdout.

#include <stdio.h>

int main( void )
{
   char strptr1[] = "This is a test of fputc!!\n";
   char *p;

   // Print line to stream using fputc.
   p = strptr1;
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;

}
```

```Output
This is a test of fputc!!
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
