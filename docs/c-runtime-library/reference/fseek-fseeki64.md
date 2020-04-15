---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: e8f6021a0b770f6b435653c190d5968f9ac50a57
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345760"
---
# <a name="fseek-_fseeki64"></a>fseek, _fseeki64

Dosya işaretçisini belirli bir konuma taşır.

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

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

*Uzaklık*<br/>
*Kaynaktan*bayt sayısı.

*Kökenli*<br/>
İlk pozisyon.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **fseek** ve **_fseeki64** 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür. Arama yapamayan aygıtlarda iade değeri tanımsızdır. *Akış* null işaretçisi ise veya *kaynak* aşağıda açıklanan izin verilen değerlerden biri **değilse,** [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini arar ve **_fseeki64 çağırır.** Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** ve return -1 **için errno** ayarlayın.

## <a name="remarks"></a>Açıklamalar

**Fseek** ve **_fseeki64** *işlevleri, akışla* ilişkili dosya işaretçisini (varsa) *kaynaktan*gelen baytları *mahsup* eden yeni bir konuma taşır. Akıştaki bir sonraki işlem yeni konumda gerçekleşir. Güncelleştirmeye açık bir akışta, bir sonraki işlem okuma veya yazma olabilir. Bağımsız değişken *in kaynağı,* STDIO'da tanımlanan aşağıdaki sabitlerden biri olmalıdır. H:

|menşe değeri|Anlamı|
|-|-|
| **SEEK_CUR** | Dosya işaretçisinin geçerli konumu. |
| **SEEK_END** | Dosyanın sonu. |
| **SEEK_SET** | Dosyanın başlangıcı. |

İşaretçiyi dosyanın herhangi bir yerinde yeniden konumlandırmak için **fseek** ve **_fseeki64** kullanabilirsiniz. İşaretçi, dosyanın sonuna da yerlebir edilebilir. **fseek** ve **_fseeki64** dosya sonu göstergesini temizler ve *akışa*karşı daha önce yapılan [tüm çağrılarüzerindeki](ungetc-ungetwc.md) etkiyi inkâr eder.

Veri ekinde bir dosya açıldığında, geçerli dosya konumu bir sonraki yazmanın nerede gerçekleşeceğine göre değil, son G/Ç işlemiyle belirlenir. Ekolarak açılan bir dosyada henüz G/Ç işlemi gerçekleşmemişse, dosya konumu dosyanın başlangıcıdır.

Metin modunda açılan akışlar için, taşıma döndürme satırı besleme çevirileri **fseek** ve **_fseeki64** beklenmeyen sonuçlar oluşturmasına neden olabileceğinden, **fseek** ve **_fseeki64** sınırlı kullanıma sahiptir. Metin modunda açılan akışlarda çalışması garanti edilen tek **fseek** ve **_fseeki64** işlemleri şunlardır:

- Kaynak değerlerinden herhangi biriyle 0 ofset ile arama.

- Bir ofset değeri ile dosyanın başından itibaren arama [ftell](ftell-ftelli64.md) veya [_ftelli64](ftell-ftelli64.md) **kullanırken** **_fseeki64**.

Ayrıca metin modunda, CTRL+Z girişte dosya sonu karakteri olarak yorumlanır. Okuma/yazma için açılan dosyalarda, [dosyanın](fopen-wfopen.md) sonunda ctrl+Z olup olmadığını kontrol edin ve mümkünse kaldırın. Bu, **fseek** ve [ftell](ftell-ftelli64.md) veya **_fseeki64** ve [_ftelli64](ftell-ftelli64.md)birleşimini kullanarak, CTRL+Z ile biten bir dosya içinde hareket etmek **fseek** veya **_fseeki64** dosyanın sonuna yakın uygunsuz şekilde hareket etmesinineden olabilir çünkü yapılır.

CRT, Byte Order Mark (BOM) ile başlayan bir dosyayı açtığında, dosya işaretçisi BOM'dan sonra (diğer bir şekilde dosyanın gerçek içeriğinin başında) konumlandırılır. Dosyanın başına ulaşmak için **fseek** gerekiyorsa, ilk konumu almak için [ftell](ftell-ftelli64.md) kullanın ve 0 konumu yerine onu **fseek.**

Bu işlev yürütme sırasında diğer iş parçacıklarını kilitler ve bu nedenle iş parçacığı güvenlidir. Kilitsiz bir sürüm için [_fseek_nolock _fseeki64_nolock](fseek-nolock-fseeki64-nolock.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**Fseek**|\<stdio.h>|
|**_fseeki64**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>
