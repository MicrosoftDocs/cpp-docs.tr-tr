---
title: _fputchar, _fputwchar
ms.date: 11/04/2016
api_name:
- _fputchar
- _fputwchar
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
- fputtchar
- _fputwchar
- fputwchar
- _fputtchar
- _fputchar
helpviewer_keywords:
- fputchar function
- standard output, writing to
- _fputtchar function
- fputwchar function
- _fputwchar function
- fputtchar function
- _fputchar function
ms.assetid: b92ff600-a924-4f2b-b0e7-3097ee31bdff
ms.openlocfilehash: b78c59b937a8854d7a36355173a1ccf4f219d541
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442976"
---
# <a name="_fputchar-_fputwchar"></a>_fputchar, _fputwchar

**Stdout**'a bir karakter yazar.

## <a name="syntax"></a>Sözdizimi

```C
int _fputchar(
   int c
);
wint_t _fputwchar(
   wchar_t c
);
```

### <a name="parameters"></a>Parametreler

*,*<br/>
Yazılacak karakter.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri yazılan karakteri döndürür. **_Fputchar**Için, **EOF** dönüş değeri bir hatayı gösterir. **_Fputwchar**Için, **weof** 'ın dönüş değeri bir hatayı gösterir. C **null**ise, bu Işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre özel durumu oluşturur. Yürütmenin devam etmesine izin veriliyorsa, **EOF** (veya **weof**) döndürür ve **errno** , **EINVAL**olarak ayarlanır.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her ikisi de **stdout** öğesine tek karakterlik *c* 'yi yazar ve göstergeyi uygun şekilde ilerletir. **_fputchar** `fputc( stdout )`eşdeğerdir. Ayrıca, **putchar**öğesine de eşdeğerdir, ancak bir işlev ve makro olarak değil, yalnızca işlev olarak uygulanır. **Fputc** ve **putchar**'ın aksıne, bu işlevler ANSI standardı ile uyumlu değildir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_fputtchar**|**_fputchar**|**_fputchar**|**_fputwchar**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fputchar**|\<stdio. h >|
|**_fputwchar**|\<stdio. h > veya \<wchar. h >|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Bu konsol ile ilişkili standart akış tutamaçları (**stdin**, **stdout**ve **stderr**), C çalışma zamanı işlevlerinin bunları UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fputchar.c
// This program uses _fputchar
// to send a character array to stdout.

#include <stdio.h>

int main( void )
{
    char strptr[] = "This is a test of _fputchar!!\n";
    char *p = NULL;

    // Print line to stream using _fputchar.
    p = strptr;
    while( (*p != '\0') && _fputchar( *(p++) ) != EOF )
      ;
}
```

```Output
This is a test of _fputchar!!
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
