---
description: 'Hakkında daha fazla bilgi edinin: fseek, _fseeki64'
title: fseek, _fseeki64
ms.date: 4/2/2020
api_name:
- _fseeki64
- fseek
- _o__fseeki64
- _o_fseek
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
ms.openlocfilehash: 7e15bd7cd273da2f73a58c2bd012670216c1938c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114331"
---
# <a name="fseek-_fseeki64"></a>fseek, _fseeki64

Dosya işaretçisini belirtilen konuma kaydırır.

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

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

*konumu*<br/>
*Kaynaktan* gelen bayt sayısı.

*başlangıç*<br/>
Başlangıç konumu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **fseek** ve **_fseeki64** 0 döndürür. Aksi takdirde, sıfır dışında bir değer döndürür. Arama yeteneğine sahip olmayan cihazlarda, dönüş değeri tanımsızdır. *Stream* null bir işaretçisiyse veya *kaynak* , aşağıda açıklanan izin verilen değerlerden biri değilse, **fseek** ve **_fseeki64** [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve-1 döndürür.

## <a name="remarks"></a>Açıklamalar

**Fseek** ve **_fseeki64** işlevleri, Stream ile ilişkili dosya işaretçisini (varsa) *kaynaktan* bayt *uzaklığa* yeni bir konuma *taşıtır* . Akıştaki bir sonraki işlem yeni konumda gerçekleşir. Güncelleştirme için açık bir akışta, sonraki işlem bir okuma veya yazma olabilir. Bağımsız değişken *kaynağı* , stdio 'da tanımlanan aşağıdaki sabitlerden biri olmalıdır. Olsun

|kaynak değeri|Anlamı|
|-|-|
| **SEEK_CUR** | Dosya işaretçisinin geçerli konumu. |
| **SEEK_END** | Dosya sonu. |
| **SEEK_SET** | Dosya başlangıcı. |

Bir dosyanın herhangi bir yerinden işaretçiyi yeniden konumlandırmak için **fseek** ve **_fseeki64** kullanabilirsiniz. İşaretçi, dosyanın sonunun ötesinde de konumlandırılmış olabilir. **fseek** ve **_fseeki64** dosya sonu göstergesini temizler ve *akışta* önceki tüm [ungetc](ungetc-ungetwc.md) çağrılarının etkisini geçersiz kılar.

Veri eklemek için bir dosya açıldığında, geçerli dosya konumu, sonraki yazmanın gerçekleştiği son g/ç işlemi tarafından belirlenir. Ekleme için açılmış bir dosya üzerinde bir g/ç işlemi henüz gerçekleşmediyse dosya konumu dosyanın başdır.

Metin modunda açılan akışlar için, **fseek** ve **_fseeki64** sınırlı bir kullanım olduğundan, satır başı satır akış çevirileri, **fseek** ve **_fseeki64** 'in beklenmedik sonuçlar üretmesine neden olabilir. Metin modunda açılan akışlar üzerinde çalışma garantisi verilen tek **fseek** ve **_fseeki64** işlemleri şunlardır:

- Kaynak değerlerinden herhangi birine göre 0 uzaklığına sahip arama.

- **_Fseeki64** kullanılırken **fseek** veya [_ftelli64](ftell-ftelli64.md) kullanılırken, dosyanın başından sonuna bir [Delta](ftell-ftelli64.md) değeri ile arama.

Ayrıca, metin modunda CTRL + Z, girişte bir dosya sonu karakteri olarak yorumlanır. Okuma/yazma için açılan dosyalarda, [fopen](fopen-wfopen.md) ve tüm ilgili yordamlar, dosyanın sonunda bir CTRL + Z olup olmadığını kontrol edin ve mümkünse kaldırın. Bu, bir CTRL + Z ile biten bir dosya içinde ilerlemek için **fseek** ve [for](ftell-ftelli64.md) veya **_fseeki64** ve [_ftelli64](ftell-ftelli64.md)birleşimini kullanmanın, **fseek** veya **_fseeki64** dosyasının sonuna doğru şekilde davranmasına neden olabileceği için yapılır.

CRT, bir bayt sırası Işaretiyle (BOM) başlayan bir dosya açtığında, dosya işaretçisi, ürün reçetesinden sonra konumlandırılır (yani, dosyanın gerçek içeriğinin başlangıcında). Dosyanın **başlangıcına yönelik bir** bilgi sahibi olmanız gerekirse, ilk konumu almak için [fsöyleyin](ftell-ftelli64.md) ' ı **kullanın ve 0 konumuna geçmek yerine** bu konuma gidin.

Bu işlev, yürütme sırasında diğer iş parçacıklarını kilitler ve bu nedenle iş parçacığı açısından güvenlidir. Kilitleme dışı bir sürüm için bkz. [_fseek_nolock, _fseeki64_nolock](fseek-nolock-fseeki64-nolock.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fseek**|\<stdio.h>|
|**_fseeki64**|\<stdio.h>|

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

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[geri sar](rewind.md)<br/>
