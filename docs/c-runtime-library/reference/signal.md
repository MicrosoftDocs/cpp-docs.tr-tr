---
title: sinyal
ms.date: 04/12/2018
apiname:
- signal
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
- signal
helpviewer_keywords:
- signal function
ms.openlocfilehash: 351bdbe1d787fc5e5d741460adfe415df7fda756
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356296"
---
# <a name="signal"></a>sinyal

Kesme sinyal işlemeyi ayarlar.

> [!IMPORTANT]
> Bu yöntem, test veya hata ayıklama senaryoları dışında bir Microsoft Store uygulamasını kapatmak için kullanmayın. Bir Store uygulamasını kapatmak için programlama veya UI yollarına göre izin verilmez [Microsoft Store ilkeleri](/legal/windows/agreements/store-policies). Daha fazla bilgi için [UWP uygulama yaşam döngüsü](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Sözdizimi

```C
void __cdecl *signal(int sig, int (*func)(int, int));
```

### <a name="parameters"></a>Parametreler

*Sig*<br/>
Sinyal değeri.

*FUNC*<br/>
İkinci parametre yürütülecek bir işlevi bir işaretçisidir. İlk parametre bir sinyal değeridir ve ikinci parametre ilk parametre SIGFPE olduğunda kullanılabilen bir alt koddur.

## <a name="return-value"></a>Dönüş Değeri

**Sinyal** func verili sinyal ile ilişkili önceki değerini döndürür. Örneğin, önceki değerini *func* olduğu **sıg_ıgn**, dönüş değeri de mi **sıg_ıgn**. Dönüş değeri **SIG_ERR** bir hata olduğunu gösterir; bu durumda, **errno** ayarlanır **EINVAL**.

Bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) dönüş kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

**Sinyal** işlevi sağlayan bir işlemin işletim sisteminden bir kesme sinyalini işlemek için çeşitli yollar birini seçin. *Sig* bağımsız değişkendir, kesme **sinyal** yanıt verir; SİNYAL içinde tanımlanan aşağıdaki bildirim sabitleri biri olmalıdır. H

|*Sig* değeri|Açıklama|
|-----------------|-----------------|
|**SIGABRT**|Olağan dışı sonlandırma|
|**SIGFPE**|Kayan nokta hatası|
|**SIGILL**|Geçersiz yönerge|
|**SIGINT**|CTRL + C sinyali|
|**SIGSEGV**|Geçersiz depo erişimi|
|**SIGTERM**|Sonlandırma isteği|

Varsa *sig* bulunmaması yukarıdaki değerleri, geçersiz parametre işleyicisi sınıfında tanımlandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve döndürür **SIG_ERR**.

Varsayılan olarak, **sinyal** değerinden bağımsız olarak çıkış kodu 3 ile arama programını sonlandırır *sig*.

> [!NOTE]
> **SIGINT** herhangi bir Win32 uygulaması için desteklenmiyor. CTRL + C kesme oluştuğunda, Win32 işletim sistemleri, özellikle bu kesmeyi işlemek için yeni bir iş parçacığı oluşturur. Bu, bir çok iş parçacıklı hale ve beklenmeyen davranışlara neden, UNIX'deki gibi bir tek iş parçacığı uygulama neden olabilir.

*Func* bağımsız değişkeni yazdığınız bir sinyal işleyicisine veya tanımlı sabitlerden birine bir adresi olan **sıg_dfl** veya **sıg_ıgn**, SİNYAL ayrıca tanımlanan. H Varsa *func* bir işlev ise verilen sinyal için sinyal işleyicisi olarak yüklenir. Sinyal işleyicinin prototipi bir biçimsel bağımsız değişken gerektirir *sig*, türü **int**. İşletim sistemi üzerinden asıl bağımsız değişkenini sağlar *sig* bir kesme oluştuğunda; bağımsız değişken kesmeyi oluşturan sinyaldir. Bu nedenle, altı bildirim sabitini (yukarıdaki tabloda listelenen), sinyal işleyicinizdeki belirlemek için hangi kesme oluştu ve uygun eylemde kullanabilirsiniz. Örneğin, çağırabilirsiniz **sinyal** iki kez için iki farklı sinyale aynı işleyiciyi atamak ve ardından test *sig* temel alınan sinyale göre farklı eylemlerde bulunmak işleyicisinde bağımsız değişken.

Kayan nokta özel durumları için sınıyorsanız (**SIGFPE**), *func* isteğe bağlı ikinci bağımsız değişken alan bir işleve işaret FLOAT tanımlanmış birçok bildirim sabitinden biridir. H, formun **FPE_xxx**. Olduğunda bir **SIGFPE** sinyali oluştuğunda, kayan nokta özel durum türünü belirleyin ve ardından uygun eylemi gerçekleştirin ikinci bağımsız değişkenin değerini teste edebilir. Bu bağımsız değişken ve olası değerleri, Microsoft uzantılarıdır.

Kayan nokta özel durumları, değerini *func* sinyal alındığında sıfırlanmaz. Kayan nokta özel durumlarından kurtulmak için try kullanma / hariç yan tümceleri kayan kapsamak için işlemleri gelin. Kullanarak kurtarmak üzere mümkündür [setjmp](setjmp.md) ile [longjmp](longjmp.md). Her iki durumda da arama işlemi yürütmeye devam eder ve kayan nokta durumunu tanımsız işlem şekilde bırakır.

Sinyal tutucusu dönerse, arama işlemi yürütmeyi, kesme sinyallerini aldığı noktanın hemen sürdürür. Bu, sinyal türü veya işletim modu ne olursa olsun doğrudur.

Belirtilen işlev yürütülmeden önce değerini *func* ayarlanır **sıg_dfl**. Sonraki kesme sinyali için açıklandığı gibi değerlendirilir **sıg_dfl**bir bölen çağrı tersini belirtmediği sürece **sinyal** değerlendirilecektir. Bu özellik çağrılan işlevdeki sinyalleri sıfırlamak için kullanabilirsiniz.

Bir kesme oluştuğunda sinyal işleyicisi rutinleri genellikle uyumsuz olarak adlandırıldığı, sinyal işleyici işleviniz bir çalıştırma zaman işlemi tamamlanmadığında ve bilinmeyen bir durumda olduğunda denetimi alabilir. Aşağıdaki listede, kullanabileceğiniz, sinyal işleme yordamınızda hangi işlevleri belirleyen sınırlamaları özetlemektedir.

- Düşük düzeyli veya STDIO yapın. H g/ç rutinleri (örneğin, **printf** veya **fread**).

- Yığın rutinlerini veya yığın rutinlerini kullanan herhangi bir rutini çağırmayın (örneğin, **malloc**, **_strdup**, veya **_putenv**). Bkz: [malloc](malloc.md) daha fazla bilgi için.

- Sistem çağrısı oluşturan bir işlev kullanmayın (örneğin, **_getcwd** veya **zaman**).

- Kullanmayın **longjmp** bir kayan nokta özel durumu kesintiye neden olmazsa (diğer bir deyişle, *sig* olduğu **SIGFPE**). Bu durumda, ilk kayan nokta paketini bir çağrısını kullanarak yeniden **_fpreset**.

- Yer paylaşımı yordamlarını kullanmayın.

Bir program yakalayacaksa, kayan nokta kodu içermesi gereken **SIGFPE** işlevini kullanarak özel durum. Programınızı kayan nokta kodu yoksa ve çalışma zamanı kitaplığının sinyal işleme kodu gerekiyorsa, geçici bir çift bildirip sıfıra atayacak yalnızca:

```C
volatile double d = 0.0f;
```

**SIGILL** ve **SIGTERM** sinyalleri Windows altında oluşturulmaz. Bunlar, ANSI uyumluluğu için dahil edilir. Kullanarak sinyal işleyiciler bu sinyaller için bu nedenle, ayarlayabilirsiniz **sinyal**, ve çağırarak bu sinyalleri açık olarak oluşturabilir [yükseltmek](raise.md).

Sinyal ayarları korunmaz yapılan çağrılar tarafından oluşturulan çağrıların ürettiği işlemlerde de [_exec](../../c-runtime-library/exec-wexec-functions.md) veya [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) işlevleri. Sinyal ayarları yeni süreç içerisinde varsayılan değerlerine sıfırlanır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**signal**|\<Signal.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir **sinyal** bazı özel davranışların eklenmesi için **SIGABRT** sinyal. İptal davranışını hakkında ek bilgi için bkz: [_set_abort_behavior](set-abort-behavior.md).

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

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_fpreset](fpreset.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
