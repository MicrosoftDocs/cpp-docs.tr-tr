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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: c5208c86484e1d9478f3879d91b32d57ba7c4a3a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912892"
---
# <a name="fflush"></a>fflush

Bir akışı temizler.

## <a name="syntax"></a>Sözdizimi

```C
int fflush(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

ara bellek başarıyla temizleniyorsa **fflush** 0 döndürür. 0 değeri, belirtilen akışın arabelleği olmadığı veya yalnızca okuma için açık olduğu durumlarda da döndürülür. **EOF** dönüş değeri bir hatayı gösterir.

> [!NOTE]
> **Fflush** **EOF**döndürürse, veriler bir yazma hatası nedeniyle kaybolmuş olabilir. Kritik bir hata işleyicisi ayarlarken, **setvarabelleğe** işlevi ile arabelleğe almayı kapatmak veya akış g/ç işlevleri yerine **_open**, **_close**ve **_write** gibi alt düzey g/ç yordamlarını kullanmak en güvenli hale gelir.

## <a name="remarks"></a>Açıklamalar

**Fflush** işlevi akış *akışını*temizler. Akış yazma modunda açılırsa veya güncelleştirme modunda açıldıysa ve son işlem bir yazarsa, akış arabelleğinin içeriği temel alınan dosyaya veya cihaza yazılır ve arabellek atılır. Akış okuma modunda açılırsa veya akışın arabelleği yoksa, **fflush** çağrısının hiçbir etkisi olmaz ve herhangi bir arabellek tutulur. **Fflush** çağrısı, akış için **ungetc** öğesine yapılan önceki çağrının etkisini geçersiz kılar. Bu akış, çağrıdan sonra açık kalır.

*Stream* **null**ise, her açık akışta bir **fflush** çağrısıyla aynı davranış vardır. Yazma modunda açılan tüm akışlar ve son işlemin bir yazma işlemi olduğu güncelleştirme modunda açılan tüm akışlar. Çağrının diğer akışlar üzerinde hiçbir etkisi yoktur.

Arabellekler normalde işletim sistemi tarafından korunur. Bu, verilerin diske otomatik olarak yazılması için en iyi zamanı belirler: bir arabellek dolduğunda, bir akış kapatıldığında veya bir program normal olarak akışı kapatmadan sonlandırıldığında. Çalışma zamanı kitaplığının diske kaydet özelliği, kritik verilerin işletim sistemi arabellekleri yerine doğrudan diske yazılmasını sağlamanıza olanak tanır. Mevcut bir programı yeniden yazmadan, programın nesne dosyalarını COMMODE. OBJ ile bağlayarak bu özelliği etkinleştirebilirsiniz. Elde edilen yürütülebilir dosyada, tüm arabelleklerin içeriğini diske yazmak **_flushall** için çağırır. Yalnızca **_flushall** ve **FFLUSH** , Commode. obj tarafından etkilendi.

Diske işleme özelliğini denetleme hakkında daha fazla bilgi için bkz. [akış g/ç](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md)ve [_fdopen](fdopen-wfdopen.md).

Bu işlev, çağıran iş parçacığını kilitler ve bu nedenle iş parçacığı güvenlidir. Kilitleme dışı bir sürüm için bkz. **_fflush_nolock**.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fflush**|\<stdio. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_flushall](flushall.md)<br/>
[setvbuf](setvbuf.md)<br/>
