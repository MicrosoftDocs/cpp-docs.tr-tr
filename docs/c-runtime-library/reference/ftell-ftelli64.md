---
description: 'Hakkında daha fazla bilgi edinin: fsöyleyin, _ftelli64'
title: ftell, _ftelli64
ms.date: 4/2/2020
api_name:
- _ftelli64
- ftell
- _o__ftelli64
- _o_ftell
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
- _ftelli64
- ftell
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
ms.openlocfilehash: f3fec98cb9d90c8b63072a8e618f58246a6b0147
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334238"
---
# <a name="ftell-_ftelli64"></a>ftell, _ftelli64

Bir dosya işaretçisinin geçerli konumunu alır.

## <a name="syntax"></a>Sözdizimi

```C
long ftell(
   FILE *stream
);
__int64 _ftelli64(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
Hedef **Dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**fsöyleyin** ve **_ftelli64** geçerli dosya konumunu döndürür. **Fsöyleyin** ve **_ftelli64** tarafından döndürülen değer metin modunda açılan akışlar için fiziksel bayt sapmasını yansıtmayabilir, çünkü metin modu satır başı satır akışı çevirisine neden olur. Dosya konumlarına doğru dönmek için [_fseeki64](fseek-fseeki64.md) ile [fseek](fseek-fseeki64.md) veya **_ftelli64** **kullanın.** Hatada, **fsöyleyin** ve **_ftelli64** [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1L döndürür ve **errno** , errno. H içinde tanımlanan iki sabitden birine ayarlanır. **EBADF** sabiti, *Stream* bağımsız değişkeninin geçerli bir dosya işaretçisi değeri olmadığı veya açık bir dosyaya başvurmayacağı anlamına gelir. **EINVAL** , işleve geçersiz bir *akış* bağımsız değişkeninin geçirildiği anlamına gelir. Arama yeteneğine sahip olmayan cihazlarda (örneğin, terminaller ve Yazıcılar) veya *akış* açık bir dosyaya başvurmadıysa, dönüş değeri tanımsız olur.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

**Fsöyleyin** ve **_ftelli64** işlevleri, *akış* ile ilişkili dosya işaretçisinin (varsa) geçerli konumunu alır. Konum, akışın başlangıcına göre bir konum olarak ifade edilir.

Veri eklemek için bir dosya açıldığında, geçerli dosya konumu, sonraki yazmanın nerede gerçekleştiğine göre değil, son g/ç işlemi tarafından belirlenir. Örneğin, bir dosya ekleme için açılırsa ve son işlem bir okuuysa, dosya konumu sonraki yazma işleminin başlayacağı noktada, sonraki okuma işleminin başlayacağı noktasıdır. (Bir dosya ekleme için açıldığında, dosya konumu herhangi bir yazma işleminden önce dosyanın sonuna taşınır.) Ekleme için açılmış bir dosya üzerinde bir g/ç işlemi henüz gerçekleşmediyse dosya konumu dosyanın başlangıcıdır.

Metin modunda CTRL + Z, girişte dosya sonu karakteri olarak yorumlanır. Okuma/yazma için açılan dosyalarda, **fopen** ve tüm ilgili yordamlar, dosyanın sonunda bir CTRL + Z olup olmadığını kontrol edin ve mümkünse kaldırın. Bu işlem, bir CTRL + Z ile biten bir dosya içinde ilerlemek için **fsöyleyin** ve [fseek](fseek-fseeki64.md) veya **_ftelli64** ve [_fseeki64](fseek-fseeki64.md)birleşiminin kullanılması, **fsöyleyin** veya **_ftelli64** dosyasının sonuna doğru şekilde davranmasına neden olabilir.

Bu işlev, yürütme sırasında çağıran iş parçacığını kilitler ve bu nedenle iş parçacığı güvenlidir. Kilitleme dışı bir sürüm için bkz. **_ftell_nolock**.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgiler|
|--------------|---------------------|----------------------|
|**fsöyleyin**|\<stdio.h>|\<errno.h>|
|**_ftelli64**|\<stdio.h>|\<errno.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_ftell.c
// This program opens a file named CRT_FTELL.C
// for reading and tries to read 100 characters. It
// then uses ftell to determine the position of the
// file pointer and displays this position.

#include <stdio.h>

FILE *stream;

int main( void )
{
   long position;
   char list[100];
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )
   {
      // Move the pointer by reading data:
      fread( list, sizeof( char ), 100, stream );
      // Get position after read:
      position = ftell( stream );
      printf( "Position after trying to read 100 bytes: %ld\n",
              position );
      fclose( stream );
   }
}
```

```Output
Position after trying to read 100 bytes: 100
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
