---
description: 'Daha fazla bilgi edinin: tmpfile'
title: tmpfile
ms.date: 11/04/2016
api_name:
- tmpfile
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
- tmpfile
helpviewer_keywords:
- temporary files
- tmpfile function
- temporary files, creating
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
ms.openlocfilehash: 27760a7d1369a0292c6719667b8cb182ce7df815
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299520"
---
# <a name="tmpfile"></a>tmpfile

Geçici bir dosya oluşturur. Daha güvenli bir sürüm kullanılabilir olduğundan bu işlev kullanım dışıdır; bkz. [tmpfile_s](tmpfile-s.md).

## <a name="syntax"></a>Syntax

```C
FILE *tmpfile( void );
```

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **tmpfile** bir akış işaretçisi döndürür. Aksi halde, **null** bir işaretçi döndürür.

## <a name="remarks"></a>Açıklamalar

**Tmpfile** işlevi, geçici bir dosya oluşturur ve bu akışa bir işaretçi döndürür. Geçici dosya kök dizinde oluşturulur. Kök dışında bir dizinde geçici bir dosya oluşturmak için, [fopen](fopen-wfopen.md)ile birlikte [tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) veya [tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) kullanın.

Dosya açılamadığı için **tmpfile** **null** bir işaretçi döndürür. Dosya kapatıldığında, program normal olarak sonlandırıldığında veya **_rmtmp** çağrıldığında, geçerli çalışma dizininin değişmediği varsayılarak bu geçici dosya otomatik olarak silinir. Geçici dosya **w + b** (ikili okuma/yazma) modunda açılır.

TMP_MAX daha fazlasını denerseniz hata oluşabilir (bkz. STDIO. H) **tmpfile** ile çağırır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**tmpfile**|\<stdio.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

> [!NOTE]
> Bu örnek, Windows Vista 'da çalıştırmak için yönetici ayrıcalıkları gerektirir.

```C
// crt_tmpfile.c
// compile with: /W3
// This program uses tmpfile to create a
// temporary file, then deletes this file with _rmtmp.
#include <stdio.h>

int main( void )
{
   FILE *stream;
   int  i;

   // Create temporary files.
   for( i = 1; i <= 3; i++ )
   {
      if( (stream = tmpfile()) == NULL ) // C4996
      // Note: tmpfile is deprecated; consider using tmpfile_s instead
         perror( "Could not open new temporary file\n" );
      else
         printf( "Temporary file %d was created\n", i );
   }

   // Remove temporary files.
   printf( "%d temporary files deleted\n", _rmtmp() );
}
```

```Output
Temporary file 1 was created
Temporary file 2 was created
Temporary file 3 was created
3 temporary files deleted
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[_rmtmp](rmtmp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
