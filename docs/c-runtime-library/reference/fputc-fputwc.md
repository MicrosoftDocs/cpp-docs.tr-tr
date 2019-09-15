---
title: fputc, fputwc
ms.date: 11/04/2016
api_name:
- fputc
- fputwc
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
ms.openlocfilehash: 3d289e54bca53be52d0b308d759f4200eca8599c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956958"
---
# <a name="fputc-fputwc"></a>fputc, fputwc

Akışa bir karakter yazar.

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

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri yazılan karakteri döndürür. **Fputc**Için, **EOF** dönüş değeri bir hatayı gösterir. **Fputwc**Için, **weof** 'ın dönüş değeri bir hatayı gösterir. *Stream* **null**Ise, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, **EOF** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, tek bir *c* karakterini ilişkili dosya konumu göstergesi (tanımlanmışsa) tarafından belirtilen konumdaki bir dosyaya yazar ve göstergeyi uygun şekilde ilerletir. **Fputc** ve **fputwc**durumunda, dosya *Stream*ile ilişkilendirilir. Dosya konumlandırma isteklerini desteklemez veya ekleme modunda açıldıysa, karakter akışın sonuna eklenir.

Akış ANSI modunda açılırsa iki işlev aynı şekilde davranır. **fputc** Şu anda bir UNICODE akışına çıktıyı desteklemiyor.

**_Nolock** sonekine sahip sürümler, diğer iş parçacıkları tarafından girişime karşı korunmamaları dışında aynıdır. Daha fazla bilgi için bkz.[_fputc_nolock, _fputwc_nolock](fputc-nolock-fputwc-nolock.md).

Rutin olarak özgü notlar izler.

|Yordam|Açıklamalar|
|-------------|-------------|
|**fputc**|**Putc**ile eşdeğerdir, ancak bir işlev ve makro olarak değil, yalnızca işlev olarak uygulanır.|
|**fputwc**|**Fputc**'nin geniş karakterli sürümü. *Akış* metin modunda veya ikili modda açılıp açılmayacağı için çok baytlı bir karakter veya geniş karakter olarak *c* yazar.|

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputtc**|**fputc**|**fputc**|**fputwc**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fputc**|\<stdio. h >|
|**fputwc**|\<stdio. h > veya \<wchar. h >|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Bu konsol ile ilişkili standart akış tutamaçları (**stdin**, **stdout**ve **stderr**), C çalışma zamanı işlevlerinin bunları UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
