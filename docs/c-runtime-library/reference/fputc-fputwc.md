---
title: fputc, fputwc
ms.date: 4/2/2020
api_name:
- fputc
- fputwc
- _o_fputc
- _o_fputwc
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
ms.openlocfilehash: 289e1114a936bdaa41fc59a0526db006536461f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346266"
---
# <a name="fputc-fputwc"></a>fputc, fputwc

Bir akışa karakter yazar.

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

*C*<br/>
Yazılacak karakter.

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri yazılan karakteri döndürür. **Fputc**için, **EOF'nin** geri dönüş değeri bir hatayı gösterir. **Fputwc**için **WEOF'un** geri dönüş değeri bir hatayı gösterir. *Akış* **NULL**ise, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütme devam etmesine izin verilirse, onlar **EOF** dönmek ve **EINVAL** **için errno** ayarlayın.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, ilişkili dosya konum göstergesi (tanımlıysa) tarafından belirtilen konumda bir dosyaya tek karakter *c* yazar ve uygun olarak göstergeyi ilerler. **fputc** ve **fputwc**durumunda , dosya *akışı*ile ilişkilidir. Dosya konumlandırma isteklerini destekleyemiyorsa veya ek modunda açılmışsa, karakter akışın sonuna eklenir.

Akış ANSI modunda açıldığında iki işlev aynı şekilde çalışır. **fputc** şu anda unicode akışına çıkış desteklemiyor.

**_nolock** sonekli sürümler, diğer iş parçacıkları tarafından parazite karşı korunmayan sürümler dışında aynıdır. Daha fazla bilgi için[_fputc_nolock, _fputwc_nolock.](fputc-nolock-fputwc-nolock.md)

Rutine özel açıklamalar takip edin.

|Yordam|Açıklamalar|
|-------------|-------------|
|**Fputc**|**Putc**eşdeğer , ancak bir işlev ve makro olarak değil, sadece bir işlev olarak uygulanır.|
|**fputwc**|**Fputc**geniş karakterli versiyonu . *Akış* metin modunda mı yoksa ikili modda mı açıldığına göre *c'yi* çok bayt karakter veya geniş bir karakter olarak yazar.|

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputtc**|**Fputc**|**Fputc**|**fputwc**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**Fputc**|\<stdio.h>|
|**fputwc**|\<stdio.h> \<veya wchar.h>|

Konsol, Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Konsolla ilişkili standart akış kolları**stdin,** **stdout**ve **stderr,** C çalışma zamanı işlevleri UWP uygulamalarında kullanamadan önce yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
