---
title: durdur
ms.date: 4/2/2020
api_name:
- abort
- _o_abort
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- Abort
helpviewer_keywords:
- aborting current process
- abort function
- processes, aborting
ms.openlocfilehash: 1f70f54783ce6f6d28fdda028af4fd5a205aeb0b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350924"
---
# <a name="abort"></a>durdur

Geçerli işlemi iptal eder ve bir hata kodu döndürür.

> [!NOTE]
> Test veya hata ayıklama senaryoları dışında bir Microsoft Mağazası uygulamasını veya Evrensel Windows Platformu (UWP) uygulamasını kapatmak için bu yöntemi kullanmayın. Bir Mağaza uygulamasını kapatmanın programlı veya uI yollarına [Microsoft Mağazası ilkelerine](/legal/windows/agreements/store-policies)göre izin verilmez. Daha fazla bilgi için [UWP uygulama yaşam döngüsüne](/windows/uwp/launch-resume/app-lifecycle)bakın.

## <a name="syntax"></a>Sözdizimi

```C
void abort( void );
```

## <a name="return-value"></a>Dönüş Değeri

**iptal** işlemi arama işlemine denetim döndürmez. Varsayılan olarak, bir iptal sinyali işleyicisi `SIGABRT` için denetler ve biri ayarlanırsa yükseltir. Sonra **iptal** geçerli işlemi sona erdirir ve üst işleme bir çıkış kodu döndürür.

## <a name="remarks"></a>Açıklamalar

**Microsoft'a Özgü**

Varsayılan olarak, bir uygulama hata ayıklama çalışma zamanı **abort** kitaplığıyla oluşturulduğunda, `SIGABRT` iptal yordamı yükseltilmeden önce bir hata iletisi görüntüler. Konsol modunda çalışan konsol uygulamaları için `STDERR`ileti. Pencereli modda çalışan Windows masaüstü uygulamaları ve konsol uygulamaları iletiyi bir ileti kutusunda görüntüler. İletiyi bastırmak için [_set_abort_behavior](set-abort-behavior.md) `_WRITE_ABORT_MSG` bayrağı temizlemek için _set_abort_behavior kullanın. Görüntülenen ileti, kullanılan çalışma zamanı ortamının sürümüne bağlıdır. Visual C++'ın en son sürümleri kullanılarak oluşturulmuş uygulamalariçin ileti aşağıdakilere benzer:

> R6010 - abort() çağrıldı

C çalışma zamanı kitaplığı önceki sürümlerinde, bu ileti görüntülendi:

> Bu uygulama, Runtime alışılmadık bir şekilde sonlandırmak istedi. Daha fazla bilgi için lütfen başvurunun destek ekibine başvurun.

Program hata ayıklama modunda derlendiğinde, ileti kutusu **Abort,** **Yeniden Deneme**veya **Yoksay**seçeneklerini görüntüler. Kullanıcı **Abort**seçerse, program hemen sona erer ve 3 çıkış kodu döndürür. Kullanıcı **Yeniden Deneme'yi**seçerse, varsa tam zamanında hata ayıklama için bir hata ayıklama çağrılır. Kullanıcı **Yoksay'ı**seçerse, **iptal** normal işleme devam eder.

Hem perakende hem de hata ayıklama yapılarında, **iptal** sinyali işleyicisi ayarlanıp ayarlanıp ayarlanıp ayarlmadığını denetler. Varsayılan olmayan bir sinyal işleyicisi ayarlanmışsa, **iptal** çağrıları. `raise(SIGABRT)` İptal [signal](signal.md) sinyali işleyicisi işlevini `SIGABRT` sinyalle ilişkilendirmek için sinyal işlevini kullanın. Özel eylemler gerçekleştirebilir (örneğin, kaynakları temizleyebilir veya bilgileri günlüğe kaydedebilir ve işleyici işlevinde kendi hata kodunuzla uygulamayı sonlandırabilirsiniz. Özel sinyal işleyicisi **abort** tanımlanmamışsa, iptal `SIGABRT` sinyali yükseltmez.

Varsayılan olarak, masaüstü veya konsol uygulamalarının hata ayıklama yapılarında, **iptal etme,** hataları Microsoft'a bildirmek için Windows Hata Raporlama Hizmeti mekanizmasını (eski adıyla Dr. Watson olarak bilinir) çağırır. Bu davranış, `_set_abort_behavior` `_CALL_REPORTFAULT` bayrağı arayarak, ayarlayarak veya maskeleyerek etkinleştirilebilir veya devre dışı edilebilir. Bayrak ayarlandığında, Windows "Bir sorun programın düzgün çalışmasının durmasına neden oldu" gibi bir metin içeren bir ileti kutusu görüntüler. Kullanıcı **hata** ayıklama düğmesini çağırmayı seçebilir veya işletim sistemi tarafından tanımlanan bir hata koduyla uygulamayı sonlandırmak için **Programı Kapat** düğmesini seçebilir.

Windows hata raporlama işleyicisi çağrılmazsa, çıkış kodu 3 ile işlemi [sonlandırmak](exit-exit-exit.md) için _exit **iptal** edin ve denetimi üst işleme veya işletim sistemine döndürür. `_exit`akış arabelleklerini yıkamaz `atexit` / `_onexit` veya işleme yapmaz.

CRT hata ayıklama hakkında daha fazla bilgi için [CRT Hata Ayıklama Teknikleri](/visualstudio/debugger/crt-debugging-techniques)bölümüne bakın.

**Microsoft'a Özel Son**

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Iptal**|\<process.h> \<veya stdlib.h>|

## <a name="example"></a>Örnek

Aşağıdaki program bir dosyayı açmaya çalışır ve girişim başarısız olursa iptal eder.

```C
// crt_abort.c
// compile with: /TC
// This program demonstrates the use of
// the abort function by attempting to open a file
// and aborts if the attempt fails.

#include  <stdio.h>
#include  <stdlib.h>

int main( void )
{
    FILE    *stream = NULL;
    errno_t err = 0;

    err = fopen_s(&stream, "NOSUCHF.ILE", "r" );
    if ((err != 0) || (stream == NULL))
    {
        perror( "File could not be opened" );
        abort();
    }
    else
    {
        fclose( stream );
    }
}
```

```Output
File could not be opened: No such file or directory
```

## <a name="see-also"></a>Ayrıca bkz.

[abort Kullanma](../../cpp/using-abort.md)<br/>
[abort İşlevi](../../c-language/abort-function-c.md)<br/>
[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec Fonksiyonlar](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[Yükseltmek](raise.md)<br/>
[sinyal](signal.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[_debug](../../c-runtime-library/debug.md)<br/>
[_set_abort_behavior](set-abort-behavior.md)
