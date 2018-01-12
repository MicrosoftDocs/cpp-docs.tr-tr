---
title: Sinyal | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: signal
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
f1_keywords: signal
dev_langs: C++
helpviewer_keywords: signal function
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 337bc5e222ee7fcb313d0b7ea0722dbb5cacea75
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="signal"></a>sinyal

Ayarlar sinyal işleme kesme.

> [!IMPORTANT]
> Bu yöntem, test etme veya senaryoları hata ayıklama bir Microsoft Store uygulamasını, kapatmak için kullanmayın. Bir mağaza uygulamasını kapatmak için programlı veya UI yolu göre verilmez [Microsoft Store ilkeleri](http://go.microsoft.com/fwlink/?LinkId=865936). Daha fazla bilgi için bkz: [UWP uygulama yaşam döngüsü](http://go.microsoft.com/fwlink/p/?LinkId=865934).

## <a name="syntax"></a>Sözdizimi

```C
void (__cdecl *signal(
   int sig,
   void (__cdecl *func ) (int [, int ] )))(int);
```

### <a name="parameters"></a>Parametreler
_SIG_  
Sinyal değeri.

_FUNC_  
Yürütülecek işlev. İlk parametre bir sinyal değer ve ikinci parametre ilk parametre SIGFPE olduğunda, kullanılabilir alt koddur.

## <a name="return-value"></a>Dönüş Değeri

`signal`önceki değerini döndürür _func_ verilen sinyal ile ilişkili. Örneğin, önceki değeri _func_ edildi `SIG_IGN`, dönüş değeri de mi `SIG_IGN`. Dönüş değeri `SIG_ERR` bir hata olduğunu gösterir; bu durumda, `errno` ayarlanır `EINVAL`.

Bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) dönüş kodları hakkında daha fazla bilgi.

## <a name="remarks"></a>Açıklamalar

`signal` İşlevi bir kesme sinyal işletim sisteminden işlemek için çeşitli yollardan birini seçmek bir işlemi etkinleştirir. _SIG_ olmayan bağımsız değişken olarak kesme `signal` yanıt verir; SİNYALİN tanımlanan aşağıdaki bildirim sabitlerden biri olmalıdır. H.

|_SIG_ değeri|Açıklama|
|-----------------|-----------------|
|`SIGABRT`|Olağan dışı sonlandırma|
|`SIGFPE`|Kayan nokta hatası|
|`SIGILL`|Geçersiz yönergesi|
|`SIGINT`|CTRL + C sinyali|
|`SIGSEGV`|Geçersiz depolama erişim|
|`SIGTERM`|Sonlandırma isteği|

Varsa _SIG_ bulunmaması yukarıdaki değerini geçersiz parametre işleyicisi, tanımlandığı şekilde çağrılan [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar `errno` için `EINVAL` ve döndürür `SIG_ERR`.

Varsayılan olarak, `signal` çağıran program değerini bakılmaksızın 3, çıkış koduyla sona erer _SIG_.

> [!NOTE]
> `SIGINT`herhangi bir Win32 uygulaması için desteklenmiyor. CTRL + C kesme ortaya çıktığında, Win32 işletim sistemleri, özellikle o kesme işlemek için yeni bir iş parçacığı oluşturur. Bu, birden çok iş parçacıklı haline gelir ve beklenmeyen davranışlara neden UNIX birinde gibi tek iş parçacığı uygulamaya neden olabilir.

_Func_ bağımsız değişkeni olan bir adres yazdığınız bir sinyal işleyicisine veya önceden tanımlanmış sabitleri birine `SIG_DFL` veya `SIG_IGN`, ayrıca SİNYALİN tanımlanmış. H. Varsa _func_ bir işlevi olduğunu verilen sinyal için sinyal işleyici olarak yüklenir. Sinyal işleyicinin prototip bir biçimsel bağımsız değişken gerektiriyor _SIG_, türü `int`. İşletim sistemi aracılığıyla gerçek bağımsız değişkeni sağlar _SIG_ bir kesinti oluştuğunda; kesme oluşturulan sinyal değişkendir. Bu nedenle, (yukarıdaki tabloda listelenen) altı bildirim sabitleri sinyal işleyicinizi belirlemek için hangi kesme oluştu ve uygun eylemi gerçekleştirin kullanabilirsiniz. Örneğin, çağırabilirsiniz `signal` iki kere aynı işleyici için iki farklı sinyalleri atamak ve ardından test etmek için _SIG_ farklı eylemleri işleyicinin değişkeninde temel sinyal alındı.

Kayan nokta özel durumlarını sınıyorsanız (`SIGFPE`), _func_ işaret birkaç bildirim sabitlerden birini içeren bir isteğe bağlı ikinci bağımsız değişken bir işleve — FLOAT tanımlanmış. H — biçiminde `FPE_xxx`. Zaman bir `SIGFPE` sinyal oluşur, kayan nokta özel durum türünü belirleme ve uygun eylemi gerçekleştirin ikinci bağımsız değişkenin değeri test edebilirsiniz. Bu bağımsız değişken ve olası değerleri Microsoft uzantılarıdır.

Kayan nokta özel durumlar, değeri için _func_ sinyal alındığında sıfırlanmaz. Kayan nokta özel durumlar kurtarmak için try kullanın / dışındaki kayan surround için yan tümceleri işlemleri işaret eder. Kullanarak kurtarmak üzere mümkündür [setjmp](../../c-runtime-library/reference/setjmp.md) ile [longjmp](../../c-runtime-library/reference/longjmp.md). Her iki durumda da çağırma işlemi yürütme devam eder ve kayan nokta tanımsız işleminin durumunu bırakır.

Sinyal işleyicisini döndürür, arama işlemi hangi Kesme sinyali aldı noktası hemen ardından yürütme devam ettirir. Bu tür sinyal veya işletim modu bağımsız olarak geçerlidir.

Belirtilen işlev yürütülmeden önce değerini _func_ ayarlanır `SIG_DFL`. Sonraki kesme sinyali için açıklandığı gibi davranılır `SIG_DFL`bir araya giren çağrı sürece `signal` Aksi halde belirtir. Çağrılan işlev sinyalleri sıfırlamak için bu özelliği kullanın.

Bir kesinti oluştuğunda sinyal işleyici yordamları genellikle zaman uyumsuz olarak adlandırılır çünkü sinyal işleyici işlevinizi çalıştırma işlemi tamamlanmamış bilinmeyen bir durumda olduğunda ve denetim elde edebilirsiniz. Aşağıdaki listede, sinyal işleyici yordamında kullanabilirsiniz hangi işlevleri belirlemek kısıtlamaları özetler.

- Olmayan alt düzey sorunu veya STDIO yapın. H g/ç yordamları (örneğin, `printf` veya `fread`).

- Yığın yordamları veya yığın yordamları kullanan yordamı çağırmayın (örneğin, `malloc`, `_strdup`, veya `_putenv`). Bkz: [malloc](../../c-runtime-library/reference/malloc.md) daha fazla bilgi için.

- Bir sistem çağrısı oluşturur herhangi bir işlev kullanmayın (örneğin, `_getcwd` veya `time`).

- Kullanmayın `longjmp` kesme bir kayan nokta özel durumu nedeniyle sürece (diğer bir deyişle, _SIG_ olan `SIGFPE`). Bu durumda, ilk kayan nokta paket için bir çağrı kullanılarak yeniden `_fpreset`.

- Herhangi bir katmana yordamları kullanmayın.

Yakalamak için ise bir program kayan nokta kodu içermelidir `SIGFPE` işlevini kullanarak özel durum. Programınızı kayan nokta kodu yok ve çalışma zamanı kitaplık sinyal işleme kodu gerektiriyorsa, yalnızca geçici çift bildirme ve sıfıra başlatılamadı:

`volatile double d = 0.0f;`

`SIGILL` Ve `SIGTERM` sinyalleri Windows altında oluşturulmaz. Bunlar ANSI uyumluluk için dahil edilmiştir. Bu nedenle, bu sinyalleri için sinyal işleyicileri kullanarak ayarlayabileceğiniz `signal`, ve çağırarak bu sinyalleri açıkça üretebilirsiniz [yükseltmek](../../c-runtime-library/reference/raise.md).

Sinyal ayarları korunmaz yapılan çağrılar tarafından oluşturulan oluşturulan işlemlerde `_exec` veya `_spawn` işlevleri. Sinyal ayarları, yeni işlem varsayılan değerlerine sıfırlanır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`signal`|\<Signal.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Aşağıdaki örnekte nasıl kullanılacağını gösterir `signal` bazı özel davranış eklemeyi `SIGABRT` sinyal. Durdurma davranışı hakkında ek bilgi için bkz: [_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md).

```C
// crt_signal.c
// compile with: /EHsc /W4
// Use signal to attach a signal handler to the abort routine
#include <stdlib.h>
#include <signal.h>
#include <tchar.h>

void SignalHandler(int signal)
{
    if (signal == SIGABRT) {
        // abort signal handler code
    } else {
        // ...
    }
}

int main()
{
    typedef void (*SignalHandlerPointer)(int);

    SignalHandlerPointer previousHandler;
    previousHandler = signal(SIGABRT, SignalHandler);

    abort();
}
```

```Output
This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)  
[abort](../../c-runtime-library/reference/abort.md)  
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)  
[exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)  
[_fpreset](../../c-runtime-library/reference/fpreset.md)  
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)  
