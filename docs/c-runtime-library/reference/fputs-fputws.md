---
description: 'Daha fazla bilgi edinin: fkoyar, fputws'
title: fputs, fputws
ms.date: 03/02/2021
api_name:
- fputs
- fputws
- _o_fputs
- _o_fputws
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
- fputs
- fputws
- _fputts
helpviewer_keywords:
- streams, writing strings to
- fputws function
- _fputts function
- fputs function
- fputts function
ms.openlocfilehash: 3b38f3c369a567c00f17a0f4d905de324100a3d4
ms.sourcegitcommit: c0c9cdae79f19655e809a4979227c51bb19cff63
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102236796"
---
# <a name="fputs-fputws"></a>`fputs`, `fputws`

Akışa bir dize yazar.

## <a name="syntax"></a>Sözdizimi

```C
int fputs(
   const char *str,
   FILE *stream
);
int fputws(
   const wchar_t *str,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*`str`*\
Çıkış dizesi.

*`stream`*\
Yapıya yönelik işaretçi **`FILE`** .

## <a name="return-value"></a>Döndürülen değer

Bu işlevlerin her biri, başarılı olursa negatif olmayan bir değer döndürür. Bir hata **`fputs`** ve **`fputws`** geri dönün **`EOF`** . *`str`* Veya *`stream`* bir null işaretçisiyse, bu Işlevler [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler öğesini **`errno`** olarak ayarlar **`EINVAL`** ve döndürür **`EOF`** .

Hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri *`str`* , *`stream`* geçerli konumdaki çıktıya kopyalar. **`fputws`** geniş karakterli bağımsız değişkeni, *`str`* *`stream`* *`stream`* sırasıyla metin modunda veya ikili modda Açıldığınıza göre çok baytlı bir karakter dizesi veya geniş karakterli bir dize olarak kopyalar. Ne işlevi, Sonlandırıcı null karakterini kopyalar.

Akış ANSI modunda açılırsa iki işlev aynı şekilde davranır. **`fputs`** Şu anda UNICODE bir akışa çıktıyı desteklememektedir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içinde küresel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel metin rutin eşlemeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**`_fputts`**|**`fputs`**|**`fputs`**|**`fputws`**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**`fputs`**|\<stdio.h>|
|**`fputws`**|\<stdio.h> veya \<wchar.h>|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. ,, Ve konsolu ile ilişkili standart akış tutamaçları, **`stdin`** **`stdout`** **`stderr`** C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fputs.c
// This program uses fputs to write
// a single line to the stdout stream.

#include <stdio.h>

int main( void )
{
   fputs( "Hello world from fputs.\n", stdout );
}
```

```Output
Hello world from fputs.
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)\
[`fgets`, `fgetws`](fgets-fgetws.md)\
[`gets`, `_getws`](../../c-runtime-library/gets-getws.md)\
[`puts`, `_putws`](puts-putws.md)
