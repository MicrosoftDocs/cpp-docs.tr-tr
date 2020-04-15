---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: bfe79610161a7f4032517d9f7eaa0de50be18e50
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345622"
---
# <a name="ftell-_ftelli64"></a>ftell, _ftelli64

Dosya işaretçisinin geçerli konumunu alır.

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

*Akışı*<br/>
Hedef **DOSYA** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**ftell** ve **_ftelli64** geçerli dosya konumunu döndürün. Metin modu satır başı satır besleme çevirisine neden olduğundan, **ftell** ve **_ftelli64** tarafından döndürülen değer, metin modunda açılan akışlar için fiziksel bayt mahsupunu yansıtmayabilir. Dosya konumlarına doğru dönmek için [fseek](fseek-fseeki64.md) veya **_ftelli64** ile **ftell** kullanın [_fseeki64.](fseek-fseeki64.md) Hata da, **ftell** ve **_ftelli64,** [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, bu işlevler -1L döndürdü ve ERRNO'da tanımlanan iki sabitin birine **errno** ayarlar. H. **EBADF** *sabiti, akış* bağımsız değişkeninin geçerli bir dosya işaretçisi değeri olmadığı veya açık bir dosyaya başvurmadığı anlamına gelir. **EINVAL,** işleve geçersiz bir *akış* bağımsız değişkeni geçtiği anlamına gelir. Arama yapamayan aygıtlarda (terminaller ve yazıcılar gibi) veya *akış* açık bir dosyaya atıfta bulunmuyorsa, iade değeri tanımsızdır.

Bunlar ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

**Ftell** ve **_ftelli64** işlevleri *akışla*ilişkili dosya işaretçisinin (varsa) geçerli konumunu alır. Konum, akışın başına göre bir ofset olarak ifade edilir.

Veri ekleyen bir dosya açıldığında, geçerli dosya konumunun bir sonraki yazmanın nerede gerçekleşeceğine göre değil, son G/Ç işlemiyle belirlendiğini unutmayın. Örneğin, bir dosya ek için açılmışsa ve son işlem okunduysa, dosya konumu bir sonraki okuma işleminin başlatılabildiği noktadır, bir sonraki yazmanın başlayacağı nokta değildir. (Bir dosya ekolarak açıldığında, dosya konumu herhangi bir yazma işleminden önce dosyanın sonuna taşınır.) Ek olarak açılan bir dosyada henüz G/Ç işlemi gerçekleşmemişse, dosya konumu dosyanın başlangıcıdır.

Metin modunda, CTRL+Z girişte dosya sonu karakteri olarak yorumlanır. Okuma/yazma için açılan dosyalarda, **dosyanın** sonunda ctrl+Z olup olmadığını kontrol edin ve mümkünse kaldırın. Bu, ctrl+Z ile biten bir dosya içinde hareket etmek için **ftell** ve [fseek](fseek-fseeki64.md) veya **_ftelli64** ve [_fseeki64](fseek-fseeki64.md)birleşimini kullanarak **ftell** veya **_ftelli64** dosyanın sonuna yakın uygunsuz bir şekilde hareket etmek neden olabilir çünkü yapılır.

Bu işlev yürütme sırasında arama iş parçacığı kilitler ve bu nedenle iş parçacığı güvenlidir. Kilitlenmeyen bir sürüm için **_ftell_nolock**bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|
|--------------|---------------------|----------------------|
|**Ftell**|\<stdio.h>|\<errno.h>|
|**_ftelli64**|\<stdio.h>|\<errno.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
