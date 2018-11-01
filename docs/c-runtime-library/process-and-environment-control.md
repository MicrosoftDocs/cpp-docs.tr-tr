---
title: Süreç ve Ortam Denetimi
ms.date: 11/04/2016
f1_keywords:
- c.programs
helpviewer_keywords:
- processes, stopping
- processes, administrative tasks
- parent process
- processes, starting
- environment control routines
- process control routines
ms.assetid: 7fde74c3-c2a6-4d15-84b8-092160d60c3e
ms.openlocfilehash: 74194311eb33a23de5643b3cb956c2e3f752dea0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525625"
---
# <a name="process-and-environment-control"></a>Süreç ve Ortam Denetimi

Başlatma, durdurma ve bir programın işlemlerini yönetmek için işlem denetim yordamları kullanın. İşletim sistemi ortamı hakkında bilgi edinin ve ortam denetimi yordamları kullanın.

## <a name="process-and-environment-control-functions"></a>İşlem ve ortam denetimi işlevleri

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[abort](../c-runtime-library/reference/abort.md)|Arabellekler temizlemeye veya kaydettirilmiş işlevlerini çağırma olmadan işlem iptal **atexit** ve **_onexit**|
|[Assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Test için mantık hatası|
|[_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makroları|Benzer şekilde **assert**, ancak yalnızca çalışma zamanı kitaplıklarının hata ayıklama sürümleri kullanılabilir|
|[atexit](../c-runtime-library/reference/atexit.md)|Program sonlandırma yürütmeyi için zamanlama rutinleri|
|[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)|Bir Windows işletim sistemi işlemi yeni bir iş parçacığı oluşturma|
|[_cexit](../c-runtime-library/reference/cexit-c-exit.md)|Gerçekleştirmek **çıkmak** sonlandırma yordamları (örneğin, arabellekler temizleme), ardından dönün denetim çağırma program işlemi sonlandırmaz|
|[_c_exit](../c-runtime-library/reference/cexit-c-exit.md)|Gerçekleştirmek **_exit** sonlandırma yordamları çıkacak denetim çağırma program işlemi sonlandırmaz|
|[_cwait](../c-runtime-library/reference/cwait.md)|Başka bir işlem sonlanana kadar bekleyin|
|[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)|Bir Windows işletim sistemi iş parçacığı sonlandırma|
|[_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)|Bağımsız değişken listesiyle yeni işlemi yürütmek|
|[_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)|Bağımsız değişken listesiyle ve belirli bir ortam yeni işlemi yürütmek|
|[_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|Kullanarak yeni işlemi yürütmek **yolu** değişken ve bağımsız değişken listesi|
|[_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|Kullanarak yeni işlemi yürütmek **yolu** değişken, belirli bir ortam ve bağımsız değişken listesi|
|[_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)|Bağımsız değişken dizisi olan yeni işlemi yürütmek|
|[_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)|Bağımsız değişken dizisi ve ortam verilen yeni işlemi yürütmek|
|[_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|Kullanarak yeni işlemi yürütmek **yolu** değişken ve bağımsız değişken dizisi|
|[_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|Kullanarak yeni işlemi yürütmek **yolu** belirli bir bağımsız değişken dizisi ve ortam değişkeni|
|[Çıkış](../c-runtime-library/reference/exit-exit-exit.md)|Tarafından kaydedilen işlevlerini **atexit** ve **_onexit**, tüm arabelleklerini, yakın tüm dosyaları açma işlemi|
|[_exit](../c-runtime-library/reference/exit-exit-exit.md)|İşlemi hemen çağırmadan **atexit** veya **_onexit** ya da bir temizlemeye arabellekler|
|[GETENV, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md), [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|Ortam değişkeninin değerini alın|
|[_getpid](../c-runtime-library/reference/getpid.md)|İşlem kimlik numarasını alın|[System::Diagnostics::Process::ID](https://msdn.microsoft.com/library/system.diagnostics.process.id.aspx)|
|[longjmp](../c-runtime-library/reference/longjmp.md)|Kayıtlı bir geri yükleme stack ortamı; bir yerel olmayan yürütülecek kullanın **Git**|
|[_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|Program sonlandırma yürütmeyi için zamanlama rutinleri; uyumluluk için Microsoft C/C++ version 7.0 ve önceki sürümleri kullanın|
|[_pclose](../c-runtime-library/reference/pclose.md)|Yeni komut işlemcisini bekleyin ve ilişkili kanaldaki akışı kapatır|
|[perror, _wperror](../c-runtime-library/reference/perror-wperror.md)|Hata iletisini Yazdır|
|[_pipe](../c-runtime-library/reference/pipe.md)|Okuma ve yazma için kanal oluştur|
|[_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)|Kanal Oluştur ve komutu yürütün|
|[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md), [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|Ekleme veya ortam değişkeninin değerini değiştirme|
|[raise](../c-runtime-library/reference/raise.md)|Çağırma işlemi için sinyal gönderin|
|[setjmp](../c-runtime-library/reference/setjmp.md)|Stack ortamınıza kaydedin; yerel olmayan yürütebilirsiniz **Git**|
|[signal](../c-runtime-library/reference/signal.md)|Kesme sinyalini işlemek|
|[_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|Belirtilen bağımsız değişken listesiyle yeni işlemi yürütmek ve oluşturma|
|[_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|Belirtilen bağımsız değişken listesi ve ortam sayesinde yeni işlemi yürütmek ve oluşturma|
|[_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|Oluşturma ve yürütme işlemini kullanarak yeni **yolu** değişkeni ve belirtilen bağımsız değişken listesi|
|[_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|Oluşturma ve yürütme işlemini kullanarak yeni **yolu** değişkeni, belirtilen ortam ve bağımsız değişken listesi|
|[_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|Belirtilen bağımsız değişken dizisi olan yeni işlemi yürütmek ve oluşturma|
|[_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|Belirtilen ortam ve bağımsız değişken dizisi ile yeni işlemi yürütmek ve oluşturma|
|[_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|Oluşturma ve yürütme işlemini kullanarak yeni **yolu** değişkeni ve belirtilen bağımsız değişken dizisi|
|[_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|Oluşturma ve yürütme işlemini kullanarak yeni **yolu** değişkeni, belirtilen ortam ve bağımsız değişken dizisi|
|[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)|İşletim sistemi komutu yürütün|

Windows işletim sisteminde, üretilen işlemde spawning işleme eşdeğerdir. Herhangi bir işlem kullanabilirsiniz **_cwait** için işlem kimliği bilinen diğer işlemin tamamlanmasını beklemek için.

Arasındaki fark **_exec** ve **_spawn** ailesinden olan bir **_spawn** işlevi döndürebilir denetimi yeni işlemden çağırma işlemine. İçinde bir **_spawn** işlev, her iki arama işlemi ve yeni işlem bellekte mevcut sürece **_P_OVERLAY** belirtilir. İçinde bir **_exec** işlevi, yeni işlem yer paylaşımları arama işlemek için yeni bir işlem yürütme işlemini başlatmadan girişimi sırasında bir hata gerçekleşmediği sürece denetimi çağırma işlemine geri döndürülemez.

İşlevler arasındaki farklar **_exec** ailesi, yanı sıra içinde arasından **_spawn** ailesi, yeni bir işlem, formun hangi bağımsız olarak yürütülecek dosyayı bulmak için yöntem içerir Aşağıdaki tabloda gösterildiği gibi yeni işlem ve ortam ayarlama yöntemi geçirilir. Bağımsız değişken sayısı sabittir veya derleme zamanında bilinen bir bağımsız değişken listesi geçirmeden bir işlev kullanın. Çalışma zamanında belirlenecek bağımsız değişken sayısı olduğunda, bağımsız değişkenleri içeren bir dizi işaretçi geçirir bir işlevi kullanın. Aşağıdaki tabloda yer alan bilgiler geniş karakter karşılıkları için de geçerlidir. **_spawn** ve **_exec** işlevleri.

### <a name="spawn-and-exec-function-families"></a>_spawn ve _exec işlevi aileleri

|İşlevler|Dosyayı bulmak için PATH değişkenini kullanın.|Bağımsız değişken geçirme kuralı|Ortam ayarları|
|---------------|--------------------------------------|----------------------------------|--------------------------|
|**_execl**, **_spawnl**|Hayır|List|Devralınan işlem çağırma|
|**_execle**, **_spawnle**|Hayır|List|Yeni işlem son bağımsız değişken olarak geçirilen ortam tablosuna bir işaretçi|
|**_execlp**, **_spawnlp**|Evet|List|Devralınan işlem çağırma|
|**_execvpe**, **_spawnvpe**|Evet|Dizi|Yeni işlem son bağımsız değişken olarak geçirilen ortam tablosuna bir işaretçi|
|**_execlpe**, **_spawnlpe**|Evet|List|Yeni işlem son bağımsız değişken olarak geçirilen ortam tablosuna bir işaretçi|
|**_execv**, **_spawnv**|Hayır|Dizi|Devralınan işlem çağırma|
|**_execve**, **_spawnve**|Hayır|Dizi|Yeni işlem son bağımsız değişken olarak geçirilen ortam tablosuna bir işaretçi|
|**_execvp**, **_spawnvp**|Evet|Dizi|Devralınan işlem çağırma|

## <a name="see-also"></a>Ayrıca Bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
