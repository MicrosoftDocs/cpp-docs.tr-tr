---
title: geri sar
ms.date: 11/04/2016
api_name:
- rewind
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
- rewind
helpviewer_keywords:
- rewind function
- repositioning file pointers
- file pointers [C++], repositioning
- file pointers [C++]
ms.assetid: 1a460ce1-28d8-4b5e-83a6-633dca29c28a
ms.openlocfilehash: 084a6f3d7e817498bffb510d865f4a32021e4ce8
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949283"
---
# <a name="rewind"></a>geri sar

Dosya işaretçisini bir dosyanın başlangıcına konumlandırır.

## <a name="syntax"></a>Sözdizimi

```C
void rewind(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

**Geri sarma** işlevi, *akış* ile ilişkili dosya işaretçisini dosyanın başlangıcına göre konumlandırır. **Geri sarma** çağrısı şuna benzer

**(void) fseek (** _Stream_ **, 0l, SEEK_SET);**

Ancak, [fseek](fseek-fseeki64.md)aksine **geri sarma** , akış için hata göstergelerini ve dosya sonu göstergesini temizler. Ayrıca, [fseek](fseek-fseeki64.md)'ın aksine, **geri sarma** , işaretçinin başarıyla taşındığını göstermek için bir değer döndürmez.

Klavye arabelleğini temizlemek için, varsayılan olarak klavye ile ilişkili akış **stdin**ile **geri sarma** kullanın.

Stream **null** Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev döndürür ve **errno** , **EINVAL**olarak ayarlanır.

Bu ve diğer hata kodları hakkında bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**rewind**|\<stdio. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_rewind.c
/* This program first opens a file named
* crt_rewind.out for input and output and writes two
* integers to the file. Next, it uses rewind to
* reposition the file pointer to the beginning of
* the file and reads the data back in.
*/
#include <stdio.h>

int main( void )
{
   FILE *stream;
   int data1, data2;

   data1 = 1;
   data2 = -37;

   fopen_s( &stream, "crt_rewind.out", "w+" );
   if( stream != NULL )
   {
      fprintf( stream, "%d %d", data1, data2 );
      printf( "The values written are: %d and %d\n", data1, data2 );
      rewind( stream );
      fscanf_s( stream, "%d %d", &data1, &data2 );
      printf( "The values read are: %d and %d\n", data1, data2 );
      fclose( stream );
   }
}
```

### <a name="output"></a>Çıkış

```Output
The values written are: 1 and -37
The values read are: 1 and -37
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
