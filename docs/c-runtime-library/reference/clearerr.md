---
title: clearerr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- clearerr
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
- clearerr
dev_langs:
- C++
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr function
ms.assetid: a9711cd4-3335-43d4-a018-87bbac5b3bac
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8fbca4b6e6083cb22bc559b7bad7e75b00b8885c
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="clearerr"></a>clearerr

Bir akış için hata göstergesi sıfırlar. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [clearerr_s](clearerr-s.md).

## <a name="syntax"></a>Sözdizimi

```C
void clearerr(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Akış* işaretçi **dosya** yapısı.

## <a name="remarks"></a>Açıklamalar

**Clearerr** işlevi sıfırlar için dosya sonu göstergesi ve hata göstergesi *akış*. Hata göstergeleri otomatik olarak temizlenmez; Belirtilen bir akış için hata göstergesi ayarladıktan sonra bir hata değeri kadar döndürmek Bu akış işlemleri devam **clearerr**, [fseek](fseek-fseeki64.md), **fsetpos**, veya [geri sarma](rewind.md) olarak adlandırılır.

Varsa *akış* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve döndürür. Daha fazla bilgi için **errno** ve hata kodları bakın [errno sabitleri](../../c-runtime-library/errno-constants.md).

Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [clearerr_s](clearerr-s.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**clearerr**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_clearerr.c
// This program creates an error
// on the standard input stream, then clears
// it so that future reads won't fail.

#include <stdio.h>

int main( void )
{
   int c;
   // Create an error by writing to standard input.
   putc( 'c', stdin );
   if( ferror( stdin ) )
   {
      perror( "Write error" );
      clearerr( stdin );
   }

   // See if read causes an error.
   printf( "Will input cause an error? " );
   c = getc( stdin );
   if( ferror( stdin ) )
   {
      perror( "Read error" );
      clearerr( stdin );
   }
   else
      printf( "No read error\n" );
}
```

```Output

n

```

```Output

      nWrite error: No error
Will input cause an error? n
No read error
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata İşleme](../../c-runtime-library/error-handling-crt.md)<br/>
[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
