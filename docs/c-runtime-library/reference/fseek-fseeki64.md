---
title: fseek, _fseeki64
ms.date: 11/04/2016
apiname:
- _fseeki64
- fseek
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
- fseek
- _fseeki64
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
ms.openlocfilehash: e5f775eab370f8f4a3b6a5c1d7f0918ec7efa3ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287592"
---
# <a name="fseek-fseeki64"></a>fseek, _fseeki64

Dosya işaretçisini, belirtilen bir konuma taşır.

## <a name="syntax"></a>Sözdizimi

```C
int fseek(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>Parametreler

*Stream*<br/>
İşaretçi **dosya** yapısı.

*uzaklık*<br/>
Bayt sayısı *kaynak*.

*Kaynak*<br/>
Başlangıç konumu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **fseek** ve **_fseeki64** 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür. Cihazlarda arama özelliğine sahip olmayan, dönüş değeri tanımsızdır. Varsa *stream* null bir işaretçiyse veya *kaynak* , aşağıda açıklanan izin verilen değerlerden biri değil **fseek** ve **_fseeki64** geçersiz çağırma bölümünde anlatıldığı gibi parametre işleyicisini [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür.

## <a name="remarks"></a>Açıklamalar

**Fseek** ve **_fseeki64** taşır (varsa) dosya işaretçisini ilişkili işlevleri *stream* yeni bir konuma *uzaklığı* bayt *kaynak*. Akışta bir sonraki işlemi yeni konumda gerçekleşecektir. Güncelleştirme için açık bir akış üzerinde okuma veya yazma sonraki işlemi olabilir. Bağımsız değişken *kaynak* STDIO içinde tanımlı sabitlerden biri olmalıdır. Y:

|Kaynak değeri|Açıklama|
|-|-|
| **SEEK_CUR** | Dosya işaretçisini geçerli konumu. |
| **SEEK_END** | Dosya sonu. |
| **SEEK_SET** | Dosyasının başında. |

Kullanabileceğiniz **fseek** ve **_fseeki64** işaretçi, bir dosyada herhangi bir yerde yeniden konumlandırmak için. İşaretçi de dosya sonunu aşan konumlandırılmalıdır. **fseek** ve **_fseeki64** dosya sonu göstergesini temizler ve tüm önceki etkisini verilerek [ungetc](ungetc-ungetwc.md) karşı çağırır *stream*.

Bir dosya veri ekleme için açıldığında, geçerli dosya konumu değildir burada sonraki yazma oluşacak tarafından son g/ç işlemi tarafından belirlenir. G/ç işlemi yok, henüz ekleme için açılan bir dosyadaki oluştuysa dosya konumunu dosyanın başlangıcıdır.

Metin modunda açılmış olan akış için **fseek** ve **_fseeki64** kullanın, satır başı satır besleme çevirileri neden olabileceği için sınırlı **fseek** ve **_ fseeki64** beklenmedik sonuçlar doğurmasına. Yalnızca **fseek** ve **_fseeki64** metin modunda açılmış olan akış üzerinde çalışacağı garanti işlemleri:

- 0 kaynak değerlerden herhangi birine göre bir uzaklık ile arama.

- Dosyanın bir uzaklık değeri ile baştan arama çağrısından döndürülen [ftell](ftell-ftelli64.md) kullanırken **fseek** veya [_ftelli64](ftell-ftelli64.md) kullanırken **_fseeki64**.

Ayrıca metin modunda, CTRL + Z girişteki bir dosya sonu karakteri olarak yorumlanır. Okuma/yazma için açılan dosyalarda [fopen](fopen-wfopen.md) ve tüm ilgili yordamları dosyanın sonunda bir CTRL + Z kontrol ve mümkünse kaldırın. Birleşimi kullanıldığından yapıldığını **fseek** ve [ftell](ftell-ftelli64.md) veya **_fseeki64** ve [_ftelli64](ftell-ftelli64.md), biten bir dosya içinde taşımak için CTRL + Z neden **fseek** veya **_fseeki64** dosyanın sonuna yakın yanlış davranmasına.

CRT bir bayt sırası işareti (BOM) ile başlayan bir dosyayı açtığında dosya işaretçisini BOM sonra konumlandırılmış (diğer bir deyişle, dosyanın gerçek içeriği başında). Gerekirse **fseek** dosyanın başına kullanın [ftell](ftell-ftelli64.md) ilk konumunu almak için ve **fseek** bunu yerine 0 konumuna.

Bu işlev, yürütme sırasında diğer iş parçacıklarını kilitler ve bu nedenle iş parçacığı açısından güvenlidir. Kilitleme yapılmayan bir sürüm için bkz. [_fseek_nolock, _fseeki64_nolock](fseek-nolock-fseeki64-nolock.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fseek**|\<stdio.h >|
|**_fseeki64**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fseek.c
// This program opens the file FSEEK.OUT and
// moves the pointer to the file's beginning.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char line[81];
   int  result;

   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )
   {
      printf( "The file fseek.out was not opened\n" );
      return -1;
   }
   fprintf( stream, "The fseek begins here: "
                    "This is the file 'fseek.out'.\n" );
   result = fseek( stream, 23L, SEEK_SET);
   if( result )
      perror( "Fseek failed" );
   else
   {
      printf( "File pointer is set to middle of first line.\n" );
      fgets( line, 80, stream );
      printf( "%s", line );
    }
   fclose( stream );
}
```

```Output
File pointer is set to middle of first line.
This is the file 'fseek.out'.
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>
