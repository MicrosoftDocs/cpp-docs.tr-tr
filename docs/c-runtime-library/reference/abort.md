---
title: Abort | Microsoft Docs
ms.custom: ''
ms.date: 1/02/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- aborting current process
- abort function
- processes, aborting
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f66c1fc650582dba99ad314d8202b3c2d2516e26
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="abort"></a>durdur

Geçerli işlem iptal eder ve bir hata kodu döndürür.

> [!NOTE]
> Bu yöntem, bir Microsoft Store uygulama veya bir evrensel Windows Platformu (UWP) uygulamasını dışında test veya senaryoları hata ayıklama kapatmak için kullanmayın. Bir mağaza uygulamasını kapatmak için programlı veya UI yolu göre verilmez [Microsoft Store ilkeleri](/legal/windows/agreements/store-policies). Daha fazla bilgi için bkz: [UWP uygulama yaşam döngüsü](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Sözdizimi

```c
void abort( void );
```

## <a name="return-value"></a>Dönüş Değeri

**Abort** denetim arama işlemi için döndürmüyor. Varsayılan olarak, bunu bir durdurma sinyali işleyicisini başlatır için denetler ve **SIGABRT** ayarlanmış bir durumunda. Ardından **abort** geçerli işlemini sonlandırır ve üst işlem çıkış kodu döndürür.

## <a name="remarks"></a>Açıklamalar

**Microsoft özel**

Bir uygulama hata ayıklama çalışma zamanı kitaplığı ile yapılandırıldığında varsayılan olarak, **abort** yordamı önce bir hata iletisi görüntüler **SIGABRT** tetiklenir. İleti gönderilir konsol modunda çalışan konsol uygulamaları için **STDERR**. Windows Masaüstü uygulamaları ve konsol uygulamaları pencereli modunda çalışan bir ileti kutusu içinde ileti görüntüler. İletinin gösterilmemesi için kullanmak [_set_abort_behavior](set-abort-behavior.md) temizlemek için **_WRITE_ABORT_MSG** bayrağı. Görüntülenen ileti kullanılan çalışma zamanı ortamı sürümüne bağlıdır. Visual C++ en son sürümü kullanılarak oluşturulmuş uygulamalar için bu iletiyi benzer:

> R6010 - abort() çağrıldı

C çalışma zamanı kitaplığı önceki sürümleri bu iletiyi görüntülenen:

> Bu uygulama çalışma zamanının bir biçimde sonlandırmasını istedi. Lütfen daha fazla bilgi için uygulama Destek ekibine başvurun.

Program hata ayıklama modunda derlendiğinde seçenekleri ileti kutusu görüntüler **Abort**, **yeniden deneme**, veya **Yoksay**. Kullanıcı seçerse **Abort**, program hemen sonlandırır ve 3 çıkış kodu döndürür. Kullanıcı seçerse **yeniden**, bir hata ayıklayıcısı tam zamanı hata ayıklama için varsa çağrılır. Kullanıcı seçerse **Yoksay**, **abort** normal devam ettirir.

Perakende ve hata ayıklama derlemelerinde, **abort** bir durdurma sinyali işleyicisi ayarlanmış olup olmadığını denetler. Varsayılan olmayan sinyal işleyici ayarlanmışsa **abort** çağrıları `raise(SIGABRT)`. Kullanım [sinyal](signal.md) bir durdurma sinyali işleyici işlevi ile ilişkilendirilecek işlevi **SIGABRT** sinyal. Özel eylemler gerçekleştirebilir — Örneğin, kaynakları temizlemek veya oturum bilgilerini — ve kendi hata kodu işleyici işlevindeki uygulamayla sonlanır. Hiçbir özel sinyal işleyici tanımlanmışsa **abort** yükseltmek değil **SIGABRT** sinyal.

Varsayılan olarak, masaüstü veya konsol uygulamaların olmayan hata ayıklama derlemelerinde **abort** (eski adıyla Dr. Windows Hata Raporlama hizmeti mekanizması çağırır Watson) Microsoft'a rapor hataları. Bu davranış etkin ya da çağırarak devre dışı **_set_abort_behavior** ve ayarlama veya maskeleme **_CALL_REPORTFAULT** bayrağı. Bayrağı ayarlandığında, Windows "programın düzgün çalışmayı durdurmasına neden bir şey bir sorunu." gibi metni içeren bir ileti kutusu görüntüler. Kullanıcı bir hata ayıklayıcısı ile çağrılacak seçebilir bir **hata ayıklama** düğmesini veya seçin **Programı Kapat** işletim sistemi tarafından tanımlanan bir hata kodu ile uygulama sonlandırmak için düğmesi.

Windows hata bildirimi işleyici, ardından değil çağrılırsa **abort** çağrıları [_exit](exit-exit-exit.md) çıkış kodu 3 ve döndürür denetimine üst işleme veya işletim sistemi ile işlem sonlandırılacak. **_exit** bırakmaz flush akış arabellekleri veya yapmak **atexit**/**_onexit** işleme.

CRT hata ayıklama hakkında daha fazla bilgi için bkz: [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

**Son Microsoft özel**

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**abort**|\<Process.h > veya \<stdlib.h >|

## <a name="example"></a>Örnek

Aşağıdaki programı bir dosyayı açmayı denediğinde ve deneme başarısız olursa durdurur.

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
[_set_abort_behavior](set-abort-behavior.md)<br/>
