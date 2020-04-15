---
title: fflush
ms.date: 4/2/2020
api_name:
- fflush
- _o_fflush
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
- fflush
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
ms.openlocfilehash: 401f715e99e6304f0726c8b9c96a71d9582dbc1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347161"
---
# <a name="fflush"></a>fflush

Bir dereyi temizler.

## <a name="syntax"></a>Sözdizimi

```C
int fflush(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**arabellek** başarıyla temizlenirse fflush 0 döndürür. Belirtilen akış arabellek veya yalnızca okumak için açık olduğu durumlarda 0 değeri de döndürülür. **EOF'nin** geri dönüş değeri bir hatayı gösterir.

> [!NOTE]
> **Fflush** **EOF**döndürürse, veri bir yazma hatası nedeniyle kaybolmuş olabilir. Kritik bir hata işleyicisi ayarlarken, arabelleğe alma işlemini **setvbuf** işleviyle kapatmak veya akış G/Ç işlevleri yerine **_open,** **_close**ve **_write** gibi düşük düzeyli G/Ç yordamları kullanmak en güvenlisi dir.

## <a name="remarks"></a>Açıklamalar

**Fflush** işlevi akış *akışını*temizler. Akış yazma modunda açılmışsa veya güncelleştirme modunda açılmışsa ve son işlem bir yazmaysa, akış arabelleği içeriği altta yatan dosyaya veya aygıta yazılır ve arabellek atılır. Akış okuma modunda açılmışsa veya akış arabelleği yoksa, **fflush** çağrısının etkisi yoktur ve arabellek korunur. **Fflush** için bir çağrı akış için **ungetc** için önceki herhangi bir çağrının etkisini inkar eder. Aramadan sonra akış açık kalır.

*Akış* **NULL**ise, davranış her açık akışta **fflush** için bir çağrı aynıdır. Tüm akışlar yazma modunda açılır ve tüm akışlar son işlemin bir yazma olduğu güncelleştirme modunda açılır. Aramanın diğer akışlar üzerinde hiçbir etkisi yoktur.

Arabellekler normalde, verileri diske otomatik olarak yazmak için en uygun zamanı belirleyen işletim sistemi tarafından korunur: arabellek dolduğunda, akış kapatıldığında veya bir program akışı kapatmadan normal olarak sona erdiğinde. Çalışma zamanı kitaplığı'nın diske işleme özelliği, kritik verilerin işletim sistemi arabelleklerine değil, doğrudan diske yazılmasını sağlamanızı sağlar. Varolan bir programı yeniden yazmadan, programın nesne dosyalarını COMMODE.OBJ ile bağlayarak bu özelliği etkinleştirebilirsiniz. Ortaya çıkan yürütülebilir dosyada, tüm arabelleklerin içeriğini diske yazmak **_flushall** için yapılan çağrılar. COMMODE.OBJ'den sadece **_flushall** ve **fflush** etkilenir.

Commit-to-disk özelliğini denetleme hakkında bilgi için [Bkz. Stream G/Ç](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md)ve [_fdopen.](fdopen-wfdopen.md)

Bu işlev arama iş parçacığı kilitler ve bu nedenle iş parçacığı güvenlidir. Kilitlenmeyen bir sürüm için **_fflush_nolock**bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fflush**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_fflush.c
// Compile with: cl /W4 crt_fflush.c
// This sample gets a number from the user, then writes it to a file.
// It ensures the write isn't lost on crash by calling fflush.
#include <stdio.h>

int * crash_the_program = 0;

int main(void)
{
    FILE * my_file;
    errno_t err = fopen_s(&my_file, "myfile.txt", "w");
    if (my_file && !err)
    {
        printf("Write a number: ");

        int my_number = 0;
        scanf_s("%d", &my_number);

        fprintf(my_file, "User selected %d\n", my_number);

        // Write data to a file immediately instead of buffering.
        fflush(my_file);

        if (my_number == 5)
        {
            // Without using fflush, no data was written to the file
            // prior to the crash, so the data is lost.
            *crash_the_program = 5;
        }

        // Normally, fflush is not needed as closing the file will write the buffer.
        // Note that files are automatically closed and flushed during normal termination.
        fclose(my_file);
    }
    return 0;
}
```

```Input
5
```

```myfile.txt
User selected 5
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_flushall](flushall.md)<br/>
[setvbuf](setvbuf.md)<br/>
