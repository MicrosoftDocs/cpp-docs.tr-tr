---
description: 'Daha fazla bilgi edinin: Işlem ve ortam denetimi'
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
ms.openlocfilehash: 7ba9c81aff87f6cfdf253da6a5d4504bcc59dce5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284582"
---
# <a name="process-and-environment-control"></a>Süreç ve Ortam Denetimi

Bir program içinden işlemleri başlatmak, durdurmak ve yönetmek için işlem denetimi yordamlarını kullanın. İşletim sistemi ortamı hakkında bilgi almak ve değiştirmek için ortam denetimi yordamlarını kullanın.

## <a name="process-and-environment-control-functions"></a>İşlem ve ortam denetimi Işlevleri

|Yordam|Kullanın|
|-------------|---------|
|[durdur](../c-runtime-library/reference/abort.md)|Ya da **atexit** ve **_onexit** tarafından kaydedilen arabellekleri veya çağırma işlevlerini temizlemeye gerek kalmadan işlemi durdur|
|[vermediğini](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Mantık hatası için test|
|[_ASSERT _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makrolar|**Onaylama** işlemine benzer ancak çalışma zamanı kitaplıklarının hata ayıklama sürümlerinde kullanılabilir|
|[atexit](../c-runtime-library/reference/atexit.md)|Program sonlandırmada çalışma yordamlarını zamanlama|
|[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)|Windows işletim sistemi işleminde yeni bir iş parçacığı oluşturma|
|[_cexit](../c-runtime-library/reference/cexit-c-exit.md)|**Çıkış** sonlandırma yordamlarını (Temizleme arabellekleri gibi) gerçekleştirin ve ardından işlemi sonlandırmadan denetimi çağıran programa döndürün|
|[_c_exit](../c-runtime-library/reference/cexit-c-exit.md)|**_Exit** sonlandırma yordamları gerçekleştirin ve ardından işlemi sonlandırmadan denetimi çağıran programa döndürün|
|[_cwait](../c-runtime-library/reference/cwait.md)|Başka bir işlem sonlanana kadar bekle|
|[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)|Windows işletim sistemi iş parçacığını sonlandırma|
|[_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)|Bağımsız değişken listesiyle yeni işlem Yürüt|
|[_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)|Bağımsız değişken listesiyle ve verilen ortamla yeni işlem yürütün|
|[_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|**Yol** değişkenini ve bağımsız değişken listesini kullanarak yeni işlem yürütün|
|[_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|**Yol** değişkenini, belirtilen ortamı ve bağımsız değişken listesini kullanarak yeni işlem yürütün|
|[_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)|Bağımsız değişken dizisiyle yeni işlem yürütün|
|[_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)|Bağımsız değişken dizisi ve verilen ortamla yeni işlem yürütün|
|[_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|**Yol** değişkenini ve bağımsız değişken dizisini kullanarak yeni işlem yürütün|
|[_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|**Yol** değişkenini, belirtilen ortamı ve bağımsız değişken dizisini kullanarak yeni işlem yürütün|
|[çıkıp](../c-runtime-library/reference/exit-exit-exit.md)|**Atexit** ve **_onexit** tarafından kaydedilen çağrı işlevleri, tüm arabellekleri temizler, tüm açık dosyaları kapat ve işlemi Sonlandır|
|[_exit](../c-runtime-library/reference/exit-exit-exit.md)|İşlemi, **atexit** veya **_onexit** veya reçeteye göre sarf arabellekleri olmadan hemen Sonlandır|
|[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md), [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|Ortam değişkeninin değerini Al|
|[_getpid](../c-runtime-library/reference/getpid.md)|İşlem KIMLIĞI numarasını al|
|[longjmp](../c-runtime-library/reference/longjmp.md)|Kaydedilmiş yığın ortamını geri yükleme; Yerel olarak yürütmek için kullanın **`goto`**|
|[_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|Program sonlandırmada çalışma yordamlarını zamanlayın; Microsoft C/C++ sürüm 7,0 ve öncesiyle uyumluluk için kullanın|
|[_pclose](../c-runtime-library/reference/pclose.md)|Yeni komut işlemcisi için bekleyin ve ilişkili kanalda akışı kapatın|
|[perror, _wperror](../c-runtime-library/reference/perror-wperror.md)|Yazdırma hatası iletisi|
|[_pipe](../c-runtime-library/reference/pipe.md)|Okuma ve yazma için kanal oluşturma|
|[_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)|Kanal oluşturma ve yürütme komutu|
|[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md), [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|Ortam değişkeninin değerini ekleme veya değiştirme|
|[tetikle](../c-runtime-library/reference/raise.md)|Çağırma işlemine sinyal gönder|
|[setjmp](../c-runtime-library/reference/setjmp.md)|Yığın ortamını Kaydet; Yerel olmayan yürütmek için kullanın **`goto`**|
|[sinyal](../c-runtime-library/reference/signal.md)|Tanıtıcı kesme sinyali|
|[_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|Belirtilen bağımsız değişken listesiyle yeni işlem oluştur ve Yürüt|
|[_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|Belirtilen bağımsız değişken listesi ve ortamıyla yeni işlem oluştur ve Çalıştır|
|[_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|**Yol** değişkenini ve belirtilen bağımsız değişken listesini kullanarak yeni işlem oluşturun ve yürütün|
|[_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|**Yol** değişkeni, belirtilen ortam ve bağımsız değişken listesini kullanarak yeni işlem oluşturun ve yürütün|
|[_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|Belirtilen bağımsız değişken dizisiyle yeni işlem oluştur ve Yürüt|
|[_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|Belirtilen ortam ve bağımsız değişken dizisiyle yeni işlem oluştur ve Yürüt|
|[_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|**Yol** değişkenini ve belirtilen bağımsız değişken dizisini kullanarak yeni işlem oluşturun ve yürütün|
|[_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|**Yol** değişkeni, belirtilen ortam ve bağımsız değişken dizisi kullanarak yeni işlem oluşturun ve yürütün|
|[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)|İşletim sistemi komutunu Yürüt|

Windows işletim sisteminde, üretilen işlem, üretilen işlem ile eşdeğerdir. Herhangi bir işlem, işlem KIMLIĞI bilinen diğer tüm işlemleri beklemek için **_cwait** kullanabilir.

**_Exec** ve **_spawn** aileleri arasındaki fark, bir **_spawn** işlevinin, yeni işlemden çağırma işlemine denetim döndürmesine olanak sağlar. **_Spawn** işlevinde, **_P_OVERLAY** belirtilmediği sürece hem çağıran işlem hem de yeni işlem bellekte bulunur. **_Exec** işlevinde yeni işlem çağıran işlemin konumunu, bu nedenle yeni işlemin yürütülmesini başlatma girişiminizde bir hata oluşmadığı sürece denetim çağıran işleme geri dönememelidir.

**_Exec** ailesindeki işlevler arasındaki farklar ve **_spawn** ailesinden olanlar arasında, yeni işlem olarak yürütülecek dosyayı bulma yöntemini, yeni işleme hangi bağımsız değişkenlerin geçirdiğine ve aşağıdaki tabloda gösterildiği gibi, ortamı ayarlama yöntemine dahil olmak üzere. Bağımsız değişkenlerin sayısı sabit olduğunda veya derleme zamanında bilindiğinde bağımsız değişken listesi geçen bir işlev kullanın. Bağımsız değişkenlerin sayısı çalışma zamanında belirlenebileceği zaman değişkenlerini içeren bir diziye işaretçi geçiren bir işlev kullanın. Aşağıdaki tablodaki bilgiler, **_spawn** ve **_exec** işlevlerinin geniş karakterli karşılıkları için de geçerlidir.

### <a name="_spawn-and-_exec-function-families"></a>_spawn ve _exec Işlev aileleri

|İşlevler|Dosyayı bulmak için yol değişkenini kullanın|Bağımsız değişken geçirme kuralı|Ortam ayarları|
|---------------|--------------------------------------|----------------------------------|--------------------------|
|**_execl**, **_spawnl**|Hayır|Liste|Çağıran işlemden devralındı|
|**_execle**, **_spawnle**|Hayır|Liste|Son bağımsız değişken olarak geçirilen yeni işlem için ortam tablosu işaretçisi|
|**_execlp**, **_spawnlp**|Evet|Liste|Çağıran işlemden devralındı|
|**_execvpe**, **_spawnvpe**|Evet|Dizi|Son bağımsız değişken olarak geçirilen yeni işlem için ortam tablosu işaretçisi|
|**_execlpe**, **_spawnlpe**|Evet|Liste|Son bağımsız değişken olarak geçirilen yeni işlem için ortam tablosu işaretçisi|
|**_execv**, **_spawnv**|Hayır|Dizi|Çağıran işlemden devralındı|
|**_execve**, **_spawnve**|Hayır|Dizi|Son bağımsız değişken olarak geçirilen yeni işlem için ortam tablosu işaretçisi|
|**_execvp**, **_spawnvp**|Evet|Dizi|Çağıran işlemden devralındı|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
