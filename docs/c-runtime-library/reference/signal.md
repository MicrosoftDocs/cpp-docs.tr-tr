---
title: Sinyal | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
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
ms.assetid: 094118de-d789-4063-b4f4-cffcc80bf29d
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 125512ba670c438ff7694b05fa73822273aba664
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="signal"></a>sinyal
Ayarlar sinyal işleme kesme.  
  
> [!IMPORTANT]
>  Kapatmak için bu yöntemi kullanma bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamayı test etme veya senaryoları hata ayıklama dışındaki. Kapatmak için programlı veya UI yolu bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulama bölüm 3.6 göre verilmez [Windows 8 uygulama sertifika gereksinimleri](http://go.microsoft.com/fwlink/?LinkId=262889). Daha fazla bilgi için bkz: [uygulama yaşam döngüsü (Windows mağazası uygulamaları)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void (__cdecl *signal(  
   int sig,   
   void (__cdecl *func ) (int [, int ] )))   
   (int);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `sig`  
 Sinyal değeri.  
  
 `func`  
 Yürütülecek işlev. İlk parametre bir sinyal değer ve ikinci parametre ilk parametre SIGFPE olduğunda, kullanılabilir alt koddur.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `signal`önceki değerini döndürür `func` verilen sinyal ile ilişkili. Örneğin, önceki değeri `func` edildi `SIG_IGN`, dönüş değeri de mi `SIG_IGN`. Dönüş değeri `SIG_ERR` bir hata olduğunu gösterir; bu durumda, `errno` ayarlanır `EINVAL`.  
  
 Bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) dönüş kodları hakkında daha fazla bilgi.  
  
## <a name="remarks"></a>Açıklamalar  
 `signal` İşlevi bir kesme sinyal işletim sisteminden işlemek için çeşitli yollardan birini seçmek bir işlemi etkinleştirir. `sig` Olmayan bağımsız değişken olarak kesme `signal` yanıt verir; SİNYALİN tanımlanan aşağıdaki bildirim sabitlerden biri olmalıdır. H.  
  
|`sig`değer|Açıklama|  
|-----------------|-----------------|  
|`SIGABRT`|Olağan dışı sonlandırma|  
|`SIGFPE`|Kayan nokta hatası|  
|`SIGILL`|Geçersiz yönergesi|  
|`SIGINT`|CTRL + C sinyali|  
|`SIGSEGV`|Geçersiz depolama erişim|  
|`SIGTERM`|Sonlandırma isteği|  
  
 Varsa `sig` bulunmaması yukarıdaki değerini geçersiz parametre işleyicisi, tanımlandığı şekilde çağrılan [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar `errno` için `EINVAL` ve döndürür `SIG_ERR`.  
  
 Varsayılan olarak, `signal` çıkış kodu 3, değerinden bağımsız olarak çağıran programla sonlandırır `sig`.  
  
> [!NOTE]
>  `SIGINT`herhangi bir Win32 uygulaması için desteklenmiyor. CTRL + C kesme ortaya çıktığında, Win32 işletim sistemleri, özellikle o kesme işlemek için yeni bir iş parçacığı oluşturur. Bu, birden çok iş parçacıklı haline gelir ve beklenmeyen davranışlara neden UNIX birinde gibi tek iş parçacığı uygulamaya neden olabilir.  
  
 `func` Bağımsız değişkeni olan bir adres yazdığınız bir sinyal işleyicisine veya önceden tanımlanmış sabitleri birine `SIG_DFL` veya `SIG_IGN`, ayrıca SİNYALİN tanımlanmış. H. Varsa `func` bir işlevi olduğunu verilen sinyal için sinyal işleyici olarak yüklenir. Sinyal işleyicinin prototip bir biçimsel bağımsız değişken gerektiriyor `sig`, türü `int`. İşletim sistemi aracılığıyla gerçek bağımsız değişkeni sağlar `sig` bir kesinti oluştuğunda; kesme oluşturulan sinyal değişkendir. Bu nedenle, (yukarıdaki tabloda listelenen) altı bildirim sabitleri sinyal işleyicinizi belirlemek için hangi kesme oluştu ve uygun eylemi gerçekleştirin kullanabilirsiniz. Örneğin, çağırabilirsiniz `signal` iki kere aynı işleyici için iki farklı sinyalleri atamak ve ardından test etmek için `sig` farklı eylemleri işleyicinin değişkeninde temel sinyal alındı.  
  
 Kayan nokta özel durumlarını sınıyorsanız (`SIGFPE`), `func` işaret birkaç bildirim sabitlerden birini içeren bir isteğe bağlı ikinci bağımsız değişken bir işleve — FLOAT tanımlanmış. H — biçiminde `FPE_xxx`. Zaman bir `SIGFPE` sinyal oluşur, kayan nokta özel durum türünü belirleme ve uygun eylemi gerçekleştirin ikinci bağımsız değişkenin değeri test edebilirsiniz. Bu bağımsız değişken ve olası değerleri Microsoft uzantılarıdır.  
  
 Kayan nokta özel durumlar, değeri için `func` sinyal alındığında sıfırlanmaz. Kayan nokta özel durumlar kurtarmak için try kullanın / dışındaki kayan surround için yan tümceleri işlemleri işaret eder. Kullanarak kurtarmak üzere mümkündür [setjmp](../../c-runtime-library/reference/setjmp.md) ile [longjmp](../../c-runtime-library/reference/longjmp.md). Her iki durumda da çağırma işlemi yürütme devam eder ve kayan nokta tanımsız işleminin durumunu bırakır.  
  
 Sinyal işleyicisini döndürür, arama işlemi hangi Kesme sinyali aldı noktası hemen ardından yürütme devam ettirir. Bu tür sinyal veya işletim modu bağımsız olarak geçerlidir.  
  
 Belirtilen işlev yürütülmeden önce değerini `func` ayarlanır `SIG_DFL`. Sonraki kesme sinyali için açıklandığı gibi davranılır `SIG_DFL`bir araya giren çağrı sürece `signal` Aksi halde belirtir. Çağrılan işlev sinyalleri sıfırlamak için bu özelliği kullanın.  
  
 Bir kesinti oluştuğunda sinyal işleyici yordamları genellikle zaman uyumsuz olarak adlandırılır çünkü sinyal işleyici işlevinizi çalıştırma işlemi tamamlanmamış bilinmeyen bir durumda olduğunda ve denetim elde edebilirsiniz. Aşağıdaki listede, sinyal işleyici yordamında kullanabilirsiniz hangi işlevleri belirlemek kısıtlamaları özetler.  
  
-   Olmayan alt düzey sorunu veya STDIO yapın. H g/ç yordamları (örneğin, `printf` veya `fread`).  
  
-   Yığın yordamları veya yığın yordamları kullanan yordamı çağırmayın (örneğin, `malloc`, `_strdup`, veya `_putenv`). Bkz: [malloc](../../c-runtime-library/reference/malloc.md) daha fazla bilgi için.  
  
-   Bir sistem çağrısı oluşturur herhangi bir işlev kullanmayın (örneğin, `_getcwd` veya `time`).  
  
-   Kullanmayın `longjmp` kesme bir kayan nokta özel durumu nedeniyle sürece (diğer bir deyişle, `sig` olan `SIGFPE`). Bu durumda, ilk kayan nokta paket için bir çağrı kullanılarak yeniden `_fpreset`.  
  
-   Herhangi bir katmana yordamları kullanmayın.  
  
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
  
```cpp  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [durdurma](../../c-runtime-library/reference/abort.md)   
 [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md)   
 [Çıkış, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_fpreset](../../c-runtime-library/reference/fpreset.md)   
 [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)