---
title: sinyal
ms.date: 04/12/2018
api_name:
- signal
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- signal
helpviewer_keywords:
- signal function
ms.openlocfilehash: 1dacf23b6c4f698b61c5bfe2dd2fb1ff7ee389f5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216758"
---
# <a name="signal"></a>sinyal

Kesme sinyali işlemeyi ayarlar.

> [!IMPORTANT]
> Test veya hata ayıklama senaryoları dışında Microsoft Store uygulamasını kapatmak için bu yöntemi kullanmayın. Bir mağaza uygulamasını kapatmak için programlı veya Kullanıcı arabirimi yollarına [Microsoft Store ilkelerine](/legal/windows/agreements/store-policies)göre izin verilmez. Daha fazla bilgi için bkz. [UWP uygulama yaşam döngüsü](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Söz dizimi

```C
void __cdecl *signal(int sig, int (*func)(int, int));
```

### <a name="parameters"></a>Parametreler

*za*<br/>
Sinyal değeri.

*func*<br/>
İkinci parametre, yürütülecek işleve yönelik bir işaretçidir. İlk parametre bir sinyal değeridir ve ikinci parametre ilk parametre SIGFPE olduğunda kullanılabilecek bir alt koddur.

## <a name="return-value"></a>Dönüş Değeri

**sinyal** verilen sinyalle ilişkili olan Func öğesinin önceki değerini döndürür. Örneğin, bir önceki *Func* değeri **SIG_IGN**ise, dönüş değeri de **SIG_IGN**. **SIG_ERR** dönüş değeri bir hatayı gösterir; Bu durumda, **errno** **EINVAL**olarak ayarlanır.

Dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

**Sinyal** işlevi, bir işlemin işletim sisteminden bir kesme sinyali işlemek için çeşitli yollarla seçim yapmasına olanak sağlar. *SIG* bağımsız değişkeni, **sinyalin** yanıt verdiği kesmede yapılır; Bu, SINYALDE tanımlı olan aşağıdaki bildirim sabitlerinden biri olmalıdır. Olsun.

|*SIG* değeri|Description|
|-----------------|-----------------|
|**SıGABRT**|Olağan dışı sonlandırma|
|**SıGFPE**|Kayan nokta hatası|
|**SıGıLL**|Geçersiz yönerge|
|**SıGıNT**|CTRL + C sinyali|
|**SıGSEGV**|Geçersiz depolama erişimi|
|**SıGTERM**|Sonlandırma isteği|

*SIG* , yukarıdaki değerlerden biri değilse, [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md) tanımlandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve **SIG_ERR**döndürür.

Varsayılan olarak, **sinyal** , *SIG*değerinden bağımsız olarak, çıkış kodu 3 ile çağıran programı sonlandırır.

> [!NOTE]
> **Sigint** herhangi bir Win32 uygulaması için desteklenmez. CTRL + C kesme oluştuğunda, Win32 işletim sistemleri bu kesmeyi özellikle işlemek için yeni bir iş parçacığı oluşturur. Bu, UNIX gibi tek iş parçacığı uygulamasının çok iş parçacıklı olmasına ve beklenmeyen davranışlara neden olmasına neden olabilir.

*Func* bağımsız değişkeni, yazdığınız bir sinyal işleyicisinin adresidir veya önceden tanımlanmış sabitlerden birine **SIG_DFL** ya da **SIG_IGN**ve ayrıca sinyal içinde tanımlanır. Olsun. *Func* işlevi bir işlevise, belirtilen sinyal için sinyal işleyicisi olarak yüklenir. Sinyal işleyicisinin prototipi,, *SIG*türünde bir biçimsel bağımsız değişken gerektiriyor **`int`** . Bir kesme gerçekleştiğinde, işletim sistemi *SIG* aracılığıyla gerçek bağımsız değişkeni sağlar; bağımsız değişkeni, kesmeyi oluşturan sinyaldir. Bu nedenle, hangi kesmenin gerçekleştiğini ve uygun eylemi istediğinizi öğrenmek için sinyal işleyicinizdeki altı bildirim sabitlerini (önceki tabloda listelenmiştir) kullanabilirsiniz. Örneğin, iki farklı sinyalle aynı işleyiciyi atamak için **sinyali** iki kez çağırabilir ve sonra alınan sinyallere göre farklı eylemler gerçekleştirmek için işleyicide *SIG* bağımsız değişkenini test edebilirsiniz.

Kayan nokta özel durumları (**Sigfpe**) için test ediyorsanız, *Func* , float içinde tanımlanan birkaç bildirim sabitlerinden biri olan isteğe bağlı ikinci bir bağımsız değişken alan bir işleve işaret eder. H, **FPE_xxx**. Bir **Sigfpe** sinyali oluştuğunda, kayan nokta özel durumunun türünü belirleyebilmek için ikinci bağımsız değişkenin değerini test edebilir ve ardından uygun eylemi gerçekleştirebilirsiniz. Bu bağımsız değişken ve olası değerleri Microsoft uzantılarıdır.

Kayan nokta özel durumları için, sinyal alındığında *Func* değeri sıfırlanmaz. Kayan nokta özel durumlarını kurtarmak için, kayan nokta işlemlerini çevrelemek üzere try/except yan tümcelerini kullanın. Ayrıca, [longjmp](longjmp.md)ile [setjmp](setjmp.md) kullanılarak kurtarma yapılabilir. Her iki durumda da çağıran işlem yürütmeyi sürdürür ve işlemin kayan nokta durumunu tanımsız bırakır.

Sinyal işleyicisi döndürülürse, çağıran işlem kesme sinyali aldığı noktadan sonra yürütmeyi hemen sürdürür. Bu, sinyal veya işletim modunun türü ne olursa olsun geçerlidir.

Belirtilen işlev yürütülmeden önce *Func* değeri **SIG_DFL**olarak ayarlanır. Bir sonraki kesme sinyali, bir **sinyal** çağrısı aksini belirtmediği sürece **SIG_DFL**için açıklandığı gibi değerlendirilir. Çağrılan işlevdeki sinyalleri sıfırlamak için bu özelliği kullanabilirsiniz.

Sinyal işleyici yordamları genellikle bir kesme gerçekleştiğinde zaman uyumsuz olarak çağrıldığı için, bir çalışma zamanı işlemi eksik olduğunda ve bilinmeyen bir durumda, sinyal işleyicisi işleviniz denetim alabilir. Aşağıdaki listede, sinyal işleyici yordamınız içinde kullanabileceğiniz işlevleri belirleyen kısıtlamalar özetlenmektedir.

- Düşük düzey veya STDIO vermeyin. H g/ç yordamları (örneğin, **printf** veya **fread**).

- Yığın yordamlarını veya yığın yordamlarını kullanan herhangi bir yordamı çağırmayın (örneğin, **malloc**, **_strdup**veya **_putenv**). Daha fazla bilgi için bkz. [malloc](malloc.md) .

- Bir sistem çağrısı (örneğin, **_getcwd** veya **zaman**) üreten herhangi bir işlev kullanmayın.

- Kesme bir kayan nokta özel durumu nedeniyle (yani, *SIG* **sigfpe**), **longjmp** kullanmayın. Bu durumda, ilk olarak **_fpreset**çağrısı kullanarak kayan nokta paketini yeniden başlatın.

- Herhangi bir kaplama yordamı kullanmayın.

İşlevi kullanarak **Sigfpe** özel durumunu yakalayabiliyorsanız, bir program kayan nokta kodu içermelidir. Programınız kayan nokta kodu içermiyorsa ve çalışma zamanı kitaplığının sinyal işleme kodunu gerektiriyorsa, geçici bir Double bildirin ve sıfıra başlatın:

```C
volatile double d = 0.0f;
```

**Sigill** ve **Sigterm** sinyalleri Windows altında oluşturulmaz. Bunlar ANSI uyumluluğu için eklenmiştir. Bu nedenle, **sinyali**kullanarak bu sinyaller için sinyal işleyicileri ayarlayabilir ve ayrıca [Yükselt](raise.md)'i çağırarak bu sinyalleri açıkça oluşturabilirsiniz.

Sinyal ayarları, [_exec](../../c-runtime-library/exec-wexec-functions.md) veya [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) işlevlerine yapılan çağrılar tarafından oluşturulan üretilen işlemlerde korunmaz. Sinyal ayarları, yeni işlemdeki varsayılan değerlere sıfırlanır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**sinyal**|\<signal.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, **Sigabrt** sinyaline özel bir davranış eklemek için **sinyalin** nasıl kullanılacağını gösterir. İptali davranışı hakkında daha fazla bilgi için bkz. [_set_abort_behavior](set-abort-behavior.md).

```C
// crt_signal.c
// compile with: /EHsc /W4
// Use signal to attach a signal handler to the abort routine
#include <stdlib.h>
#include <signal.h>

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

Çıktı, kullanılan çalışma zamanının sürümüne, uygulamanın bir konsol veya Windows uygulaması ve Windows kayıt defteri ayarları olmasına bağlıdır. Konsol uygulaması için, stderr 'e aşağıdaki iletiyle benzer bir ileti gönderilebilir:

```Output
Debug Error!

Program: c:\Projects\crt_signal\Debug\crt_signal.exe

R6010

- abort() has been called
```

## <a name="see-also"></a>Ayrıca bkz.

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[durdur](abort.md)<br/>
[_exec, _wexec Işlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_fpreset](fpreset.md)<br/>
[_spawn, _wspawn Işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
