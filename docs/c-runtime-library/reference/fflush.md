---
title: fflush
ms.date: 11/04/2016
apiname:
- fflush
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
- fflush
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
ms.openlocfilehash: d03d20ee5024915d0ca4c5a21db4159e8c4f876a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333988"
---
# <a name="fflush"></a>fflush

Bir akışa aktarır.

## <a name="syntax"></a>Sözdizimi

```C
int fflush(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**fflush** arabellek başarıyla temizlendi 0 döndürür. 0 değeri, belirtilen Akış Arabellek olan veya yalnızca okumak için açık olan durumlarda da döndürülür. Dönüş değeri **EOF** bir hata olduğunu gösterir.

> [!NOTE]
> Varsa **fflush** döndürür **EOF**, veriler kaybolmuş olabilir bir yazma hatası nedeniyle. Bir kritik hata işleyicisini ayarlarken, arabelleğe alma ile devre dışı bırakmak güvenli **setvbuf** işlevi veya alt düzey g/ç yordamları kullanmanız **_aç**, **_close**, ve **_write** akış g/ç işlevleri yerine.

## <a name="remarks"></a>Açıklamalar

**Fflush** işlevi stream aktarır *stream*. Akış açtıysanız yazma modu veya güncelleştirme modunda açılmış ve yazma son işlemin, temel alınan dosya veya cihaza akış arabelleğinin içeriğini yazılır ve arabellek atılır. Akış Okuma modunda açıldıysa veya Akış Arabellek, çağrı varsa **fflush** etkiye sahip değildir ve herhangi bir arabellek korunur. Bir çağrı **fflush** her çağrıda etkisini verilerek **ungetc** akış için. Stream ve çağrının ardından açık kalır.

Varsa *stream* olduğu **NULL**, davranışı bir çağrı ile aynıdır **fflush** açık her akış hakkındaki. Tüm akışları yazma modunda açılmış ve son işlemi yazma olduğu tüm akışları güncelleştirme modunda açıldığında temizlenir. Çağrı diğer akışlar üzerinde etkisi yoktur.

Arabellekler verileri otomatik olarak diske yazmak için en iyi zamanı belirler işletim sistemi tarafından normalde korunur: Arabellek dolduğunda, bir akış kapatıldığında veya ne zaman bir program akışı kapatmadan sona erer. Çalışma zamanı kitaplığının işleme disk özellik kritik verileri doğrudan disk yerine işletim sistemi arabelleklerini yazıldığından emin olanak sağlar. Varolan bir program yeniden yazma olmadan programın nesne dosyaları COMMODE.OBJ ile bağlayarak bu özelliği etkinleştirebilirsiniz. Oluşturulan yürütülebilir dosya olarak çağrılar **_flushall** arabelleklerin içeriğini diske yazma. Yalnızca **_flushall** ve **fflush** COMMODE.OBJ tarafından etkilenir.

Yürütme disk özellik denetleme hakkında daha fazla bilgi için bkz [Stream g/ç](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md), ve [_fdopen](fdopen-wfdopen.md).

Bu işlev, çağıran iş parçacığının kilitler ve bu nedenle iş parçacığı açısından güvenlidir. Kilitleme yapılmayan bir sürüm için bkz. **_fflush_nolock**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fflush**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fflush.c
#include <stdio.h>
#include <conio.h>

int main( void )
{
   int integer;
   char string[81];

   // Read each word as a string.
   printf( "Enter a sentence of four words with scanf: " );
   for( integer = 0; integer < 4; integer++ )
   {
      scanf_s( "%s", string, sizeof(string) );
      printf( "%s\n", string );
   }

   // You must flush the input buffer before using gets.
   // fflush on input stream is an extension to the C standard
   fflush( stdin );
   printf( "Enter the same sentence with gets: " );
   gets_s( string, sizeof(string) );
   printf( "%s\n", string );
}
```

```Input
This is a test
This is a test
```

```Output
Enter a sentence of four words with scanf: This is a test
This
is
a
test
Enter the same sentence with gets: This is a test
This is a test
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_flushall](flushall.md)<br/>
[setvbuf](setvbuf.md)<br/>
