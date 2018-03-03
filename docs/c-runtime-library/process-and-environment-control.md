---
title: "Süreç ve ortam denetimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- processes, stopping
- processes, administrative tasks
- parent process
- processes, starting
- environment control routines
- process control routines
ms.assetid: 7fde74c3-c2a6-4d15-84b8-092160d60c3e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cee24f0e5142af37681bd293a3be3600ddbd1cc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="process-and-environment-control"></a>Süreç ve Ortam Denetimi
İşlem Denetim yordamları başlatma, durdurma ve bir programdan işlemlerini yönetmek için kullanın. Almak ve işletim sistemi ortamı hakkındaki bilgileri değiştirmek için ortam denetimi yordamları kullanın.  
  
### <a name="process-and-environment-control-functions"></a>İşlem ve ortam denetimi işlevleri  
  
|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|-------------|---------|  
|[abort](../c-runtime-library/reference/abort.md)|Arabellek boşaltma veya tarafından kaydedilen işlevleri çağırma olmadan işlem iptal `atexit` ve`_onexit`|  
|[Assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Test mantık hatası için|  
|[_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makroları|Benzer şekilde `assert`, ancak yalnızca çalışma zamanı kitaplıkları hata ayıklama sürümlerinde kullanılabilir|  
|[atexit](../c-runtime-library/reference/atexit.md)|Program sonlandırma yürütmesi için zamanlama rutinleri|  
|[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)|Bir Windows işletim sistemi işlemi üzerinde yeni bir iş parçacığı oluşturma|  
|[_cexit](../c-runtime-library/reference/cexit-c-exit.md)|Gerçekleştirmek `exit` sonlandırma yordamları (örneğin, arabellek temizleme), sonra geri dönüp denetim çağıran program için işlem sonlandırma olmadan|  
|[_c_exit](../c-runtime-library/reference/cexit-c-exit.md)|Gerçekleştirmek `_exit` sonlandırma yordamlar, sonra geri dönüp denetim çağıran program için işlem sonlandırma olmadan|  
|[_cwait](../c-runtime-library/reference/cwait.md)|Başka bir işlem sonlanana kadar bekleyin|  
|[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)|Bir Windows işletim sistemi iş parçacığı sonlandırma|  
|[_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)|Bağımsız değişken listesiyle yeni işlem yürütme|  
|[_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)|Bağımsız değişken listesiyle ve belirli bir ortam yeni işlem yürütme|  
|[_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|Kullanarak yeni işlem yürütme `PATH` değişkeni ve bağımsız değişken listesi|  
|[_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|Kullanarak yeni işlem yürütme `PATH` değişken, belirli bir ortam ve bağımsız değişken listesi|  
|[_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)|Bağımsız değişken dizisi ile yeni işlem yürütme|  
|[_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)|Belirli bir ortam değişkeni dizi ile yeni işlem yürütme|  
|[_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|Kullanarak yeni işlem yürütme `PATH` değişkeni ve bağımsız değişken dizisi|  
|[_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|Kullanarak yeni işlem yürütme `PATH` belirli bir bağımsız değişken dizisi ve ortam değişkeni|  
|[Çıkış](../c-runtime-library/reference/exit-exit-exit.md)|Tarafından kaydedilen işlevlerini `atexit` ve `_onexit`, tüm arabellekler temizleme, Kapat tüm dosyaları ve işlemin sonlandırılmasına|  
|[_exit](../c-runtime-library/reference/exit-exit-exit.md)|İşlemi hemen çağırmadan sonlandırmak `atexit` veya `_onexit` veya arabellekleri temizleme|  
|[GETENV, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md), [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|Ortam değişkeninin değerini alın|  
|[_getpid](../c-runtime-library/reference/getpid.md)|İşlem kimliği numarasını Al|[System::Diagnostics::Process::ID](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.id.aspx)|  
|[longjmp](../c-runtime-library/reference/longjmp.md)|Kaydedilen geri yükleme yığın ortamını; bir yerel olmayan yürütmek için kullanın`goto`|  
|[_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|Program sonlandırma yürütmesi için zamanlama yordamları; Microsoft C/C++ version 7.0 ve daha önce uyumluluk için kullanın|  
|[_pclose](../c-runtime-library/reference/pclose.md)|Yeni Komut işlemcisi için bekleyin ve ilişkili kanal akışta Kapat|  
|[perror, _wperror](../c-runtime-library/reference/perror-wperror.md)|Yazdırma hata iletisi|  
|[_pipe](../c-runtime-library/reference/pipe.md)|Okuma ve yazma için kanal oluştur|  
|[_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)|Kanal oluşturma ve komut yürütme|  
|[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md), [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|Ekleme veya ortam değişkeninin değerini değiştirme|  
|[raise](../c-runtime-library/reference/raise.md)|Arama işlemi için sinyal gönderme|  
|[setjmp](../c-runtime-library/reference/setjmp.md)|Yığın ortamını kaydedin; yerel olmayan yürütmek için kullanın`goto`|  
|[signal](../c-runtime-library/reference/signal.md)|Tanıtıcı Kesme sinyali|  
|[_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|Oluşturma ve belirtilen bağımsız değişken listesiyle yeni işlem yürütme|  
|[_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|Oluşturma ve belirtilen bağımsız değişken listesi ve ortam ile yeni işlem yürütme|  
|[_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|Oluşturma ve yeni işlem kullanarak yürütme `PATH` değişkeni ve belirtilen bağımsız değişken listesi|  
|[_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|Oluşturma ve yeni işlem kullanarak yürütme `PATH` değişkeni, belirtilen ortam ve bağımsız değişken listesi|  
|[_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|Oluşturma ve belirtilen bağımsız değişken dizisi ile yeni işlem yürütme|  
|[_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|Oluşturma ve belirtilen ortam ve bağımsız değişken dizisi ile yeni işlem yürütme|  
|[_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|Oluşturma ve yeni işlem kullanarak yürütme `PATH` değişkeni ve belirtilen bağımsız değişken dizisi|  
|[_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|Oluşturma ve yeni işlem kullanarak yürütme `PATH` değişkeni, belirtilen ortam ve bağımsız değişken dizisi|  
|[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)|İşletim sistemi komutu yürütün|  
  
 Windows işletim sisteminde, oluşturulan işlemi spawning işlemi eşdeğerdir. Herhangi bir işlem kullanabilirsiniz `_cwait` işlem kimliği bilinir diğer işlemin tamamlanmasını beklemek için.  
  
 Arasındaki farkı `_exec` ve `_spawn` aileleri olan bir `_spawn` işlevi dönebilirsiniz denetim yeni işlem çağırma işlemi. İçinde bir `_spawn` işlev, arama işlemi iki ve yeni işlem bellekte mevcut sürece `_P_OVERLAY` belirtilir. İçinde bir `_exec` işlevi, arama işlem, yeni işlemin yürütülmesini Başlat girişimi sırasında bir hata oluştuğunda sürece denetim arama işlemi geri dönemezsiniz şekilde yeni işlem yer paylaşımları.  
  
 İşlevlerde arasındaki farklar `_exec` ailesi, yanı sıra de arasında `_spawn` ailesi, yeni bir işlem, formun içinde bağımsız değişken geçirilir yeni işlem ve yöntemi olarak yürütülebilir dosyaya bulma yöntemini içerir Aşağıdaki tabloda gösterildiği gibi ortamı ayarlama. Bağımsız değişken sayısı sabit olduğunda veya derleme zamanında bilinen bir bağımsız değişken listesi geçirir işlevi kullanın. Bağımsız değişken sayısı çalışma zamanında belirlenecek olduğunda bağımsız değişkenleri içeren bir dizi bir işaretçi geçirir işlevini kullanın. Aşağıdaki tabloda yer alan bilgiler joker karakter ortaklarınıza için de geçerlidir `_spawn` ve `_exec` işlevleri.  
  
### <a name="spawn-and-exec-function-families"></a>_spawn ve _exec işlevi aileleri  
  
|İşlevler|Dosyayı bulmak üzere PATH değişkeni kullanın|Bağımsız değişken geçirme kuralı|Ortam ayarları|  
|---------------|--------------------------------------|----------------------------------|--------------------------|  
|`_execl, _spawnl`|Hayır|List|İşlem çağırma devralınan|  
|`_execle, _spawnle`|Hayır|List|Son bağımsız değişken olarak geçirilen yeni işlem için ortam tabloya işaretçi|  
|`_execlp, _spawnlp`|Evet|List|İşlem çağırma devralınan|  
|`_execlpe, _spawnlpe`|Evet|List|Son bağımsız değişken olarak geçirilen yeni işlem için ortam tabloya işaretçi|  
|`_execv, _spawnv`|Hayır|Dizi|İşlem çağırma devralınan|  
|`_execve, _spawnve`|Hayır|Dizi|Son bağımsız değişken olarak geçirilen yeni işlem için ortam tabloya işaretçi|  
|`_execvp, _spawnvp`|Evet|Dizi|İşlem çağırma devralınan|  
|`_execvpe, _spawnvpe`|Evet|Dizi|Son bağımsız değişken olarak geçirilen yeni işlem için ortam tabloya işaretçi|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kategorilere Göre Çalışma Zamanı Yordamları](../c-runtime-library/run-time-routines-by-category.md)