---
title: durdur
ms.date: 1/02/2018
apiname:
- abort
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- Abort
helpviewer_keywords:
- aborting current process
- abort function
- processes, aborting
ms.openlocfilehash: d8cb190e36a64e8bd8cfcb75bc9a19c2a394fc48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62342204"
---
# <a name="abort"></a>durdur

Geçerli işlemi iptal eder ve bir hata kodu döndürür.

> [!NOTE]
> Bu yöntem, bir Microsoft Store uygulaması veya evrensel Windows Platformu (UWP) uygulamasına dışında test veya hata ayıklama senaryoları kapatmak için kullanmayın. Bir Store uygulamasını kapatmak için programlama veya UI yollarına göre izin verilmez [Microsoft Store ilkeleri](/legal/windows/agreements/store-policies). Daha fazla bilgi için [UWP uygulama yaşam döngüsü](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Sözdizimi

```C
void abort( void );
```

## <a name="return-value"></a>Dönüş Değeri

**Abort** denetimi çağırma işlemine döndürmez. Varsayılan olarak, iptal sinyali işleyicisini ve harekete geçirirse denetler `SIGABRT` biri ayarlanmışsa. Ardından **iptal** geçerli işlemi sonlandırır ve üst işleme çıkış kodu döndürür.

## <a name="remarks"></a>Açıklamalar

**Microsoft'a özgü**

Bir uygulama hata ayıklama çalışma zamanı kitaplığıyla oluşturulduğunda varsayılan olarak **iptal** yordamı önce bir hata iletisi görüntüler `SIGABRT` tetiklenir. İleti gönderilir konsol modunda çalışan konsol uygulamaları için `STDERR`. Windows Masaüstü uygulamaları ve konsol uygulamaları pencereli modda çalışan ileti bir ileti kutusunda görüntüler. Bu iletiyi engellemek için kullanın [_set_abort_behavior](set-abort-behavior.md) temizlemek için `_WRITE_ABORT_MSG` bayrağı. Görüntülenen ileti kullanılan çalışma zamanı ortamının sürümüne bağlıdır. Visual C++'ın en son sürümleri kullanılarak oluşturulan uygulamalar için mesaj bunu yeniden birleştirir:

> R6010 - abort() çağrıldı

C çalışma zamanı kitaplığının önceki sürümlerinde bu ileti görüntülendi:

> Bu uygulama, çalışma zamanının bir biçimde sonlandırmasını istedi. Lütfen daha fazla bilgi için uygulamanın Destek ekibine başvurun.

Program hata ayıklama modunda derlendiğinde, ileti kutusunda seçeneklerini görüntüler **iptal**, **yeniden**, veya **Yoksay**. Kullanıcı seçerse **iptal**, program hemen sonlanır ve bir 3 çıkış kodu döndürür. Kullanıcı seçerse **yeniden**, bir hata ayıklayıcı just-ın-time hata ayıklama için varsa çağrılır. Kullanıcı seçerse **Yoksay**, **iptal** normal işleme devam eder.

Hem tekil hem de hata ayıklama yapılarında **iptal** daha sonra iptal sinyal tutucusunun ayarlanıp ayarlanmadığını denetler. Varsayılan olmayan sinyal işleyici ayarlanırsa **iptal** çağrıları `raise(SIGABRT)`. Kullanım [sinyal](signal.md) işlevi ile bir iptal sinyal işleyicisi işlevini ilişkilendirmek için `SIGABRT` sinyal. Özel eylemler gerçekleştirebilir — Örneğin, kaynakları temizlemek veya oturum bilgilerini — ve kendi işleyici işlevindeki hata kodu ile uygulamanızı sonlandırın. Hiçbir özel sinyal tutucusu tanımlanmazsa, **iptal** yükseltmez `SIGABRT` sinyal.

Varsayılan olarak masaüstü veya konsol uygulamaların hata ayıklama olmayan yapılarında **iptal** sonra (eski adıyla Dr bilinir. Windows Hata Raporlama hizmeti mekanizmasını çağırır Watson) Microsoft'a rapor hataları. Bu davranışı etkinleştirilebilir veya devre dışı çağırarak `_set_abort_behavior` ayarlanarak veya maskelenerek `_CALL_REPORTFAULT` bayrağı. Bayrak ayarlandığında, Windows "programın düzgün çalışmayı durdurmasına neden bir sorun oluştu." gibi metin içeren bir ileti kutusu görüntüler. Kullanıcı bir hata ayıklayıcı çağırmayı seçebilir bir **hata ayıklama** düğmesini veya tercih **Programı Kapat** düğmesini işletim sistemi tarafından tanımlanan bir hata kodu ile uygulamanızı sonlandırın.

Windows hata bildirimi işleyicisi, ardından değil çağrılırsa **iptal** çağrıları [_exit](exit-exit-exit.md) çıkış kodu 3 ve döndürür denetimi üst işleme ya da işletim sistemi ile işlemi sonlandırılamıyor. `_exit` Akış arabelleklerini veya desteklemez yapmak `atexit` / `_onexit` işleniyor.

CRT hata ayıklama hakkında daha fazla bilgi için bkz. [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

**End Microsoft özgü**

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**abort**|\<Process.h > veya \<stdlib.h >|

## <a name="example"></a>Örnek

Aşağıdaki program bir dosyayı açmayı denediğinde ve deneme başarısız olursa iptal eder.

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
[exit İşlevi](../../c-language/abort-function-c.md)<br/>
[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[raise](raise.md)<br/>
[signal](signal.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
[_set_abort_behavior](set-abort-behavior.md)