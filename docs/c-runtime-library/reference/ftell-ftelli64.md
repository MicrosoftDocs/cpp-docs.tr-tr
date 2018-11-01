---
title: ftell, _ftelli64
ms.date: 11/04/2016
apiname:
- _ftelli64
- ftell
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
- _ftelli64
- ftell
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
ms.openlocfilehash: cc76ad0776ae82637b95d32cdc6254d3c40da5b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660531"
---
# <a name="ftell-ftelli64"></a>ftell, _ftelli64

Dosya işaretçisini geçerli konumunu alır.

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

*Stream*<br/>
Hedef **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**ftell** ve **_ftelli64** geçerli dosya konumu döndürür. Tarafından döndürülen değer **ftell** ve **_ftelli64** metin modunda, satır başı satır besleme çeviri neden olduğu fiziksel bayt uzaklığı için metin modunda açılmış olan akış yansıtmayabilir. Kullanım **ftell** ile [fseek](fseek-fseeki64.md) veya **_ftelli64** ile [_fseeki64](fseek-fseeki64.md) doğru dosya konumları için döndürülecek. Hata durumunda, **ftell** ve **_ftelli64** açıklandığı gibi geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Devam etmek için bu işlevler döndürür-1 L ve kümesi yürütülmesine izin veriliyorsa **errno** ERRNO içinde tanımlı iki sabitlerinden birini için. H **EBADF** sabiti anlamına gelir *stream* bağımsız değişkeni geçerli bir dosya işaretçi değeri değil veya açık olan bir dosyaya başvurmuyor. **EINVAL** geçersiz anlamına gelir *stream* bağımsız değişken işleve geçirildi. (Terminaller ve yazıcılar gibi), arama özelliğine sahip olmayan cihazlarda veya *stream* değil başvurmak için açık bir dosyayı, dönüş değeri tanımsızdır.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.

## <a name="remarks"></a>Açıklamalar

**Ftell** ve **_ftelli64** işlevleri ile ilişkili dosya işaretçisini (varsa) geçerli konumu alma *stream*. Konum, akış başlangıcına göre bir uzaklık olarak ifade edilir.

Bir dosya veri ekleme için açıldığında, geçerli dosya konumu son g/ç işlemi tarafından değil burada sonraki yazma oluşacak tarafından belirlenir olduğunu unutmayın. Örneğin, bir dosya bir ekleme için açıldığında ve okuma son işlemin, dosya konumu burada sonraki okuma işlemi, burada sonraki yazma başlatılamayan başlar noktasıdır. (Bir dosya ekleme için açıldığında, dosya konumu için dosya sonu tüm yazma işleminden önce taşınır.) G/ç işlemi yok, henüz ekleme için açılan bir dosyadaki oluştuysa dosya konumunu dosyanın başlangıcıdır.

Metin modunda, CTRL + Z girişteki bir dosya sonu karakteri olarak yorumlanır. Okuma/yazma için açılan dosyalarda **fopen** ve tüm ilgili yordamları dosyanın sonunda bir CTRL + Z kontrol ve mümkünse kaldırın. Birleşimi kullanıldığından yapıldığını **ftell** ve [fseek](fseek-fseeki64.md) veya **_ftelli64** ve [_fseeki64](fseek-fseeki64.md), biten bir dosya içinde taşımak için CTRL + Z neden **ftell** veya **_ftelli64** dosyanın sonuna yakın yanlış davranmasına.

Bu işlev, yürütme sırasında çağıran iş parçacığının kilitler ve bu nedenle iş parçacığı açısından güvenlidir. Kilitleme yapılmayan bir sürüm için bkz. **_ftell_nolock**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üst bilgiler|
|--------------|---------------------|----------------------|
|**ftell**|\<stdio.h >|\<errno.h >|
|**_ftelli64**|\<stdio.h >|\<errno.h >|

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
