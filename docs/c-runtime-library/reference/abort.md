---
title: Abort | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: abort
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
f1_keywords: Abort
dev_langs: C++
helpviewer_keywords:
- aborting current process
- abort function
- processes, aborting
ms.assetid: a797783b-40ed-4bdb-a2cd-14ffede39e8a
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3c052798cc0ee5062e2a18e498ce8759b15c44b2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="abort"></a>durdur
Geçerli işlem iptal eder ve bir hata kodu döndürür.  
  
> [!NOTE]
>  Kapatmak için bu yöntemi kullanma bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamayı test etme veya senaryoları hata ayıklama dışındaki. Kapatmak için programlı veya UI yolu bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] göre uygulama verilmez [Windows 8 uygulama sertifika gereksinimleri](http://go.microsoft.com/fwlink/?LinkId=262889). Daha fazla bilgi için bkz: [uygulama yaşam döngüsü (Windows mağazası uygulamaları)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void abort( void );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `abort`Denetim arama işlemi için döndürmez. Varsayılan olarak, bunu bir durdurma sinyali işleyicisini başlatır için denetler ve `SIGABRT` ayarlanmış bir durumunda. Ardından `abort` geçerli işlemini sonlandırır ve üst işlem çıkış kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 **Microsoft özel**  
  
 Bir uygulama hata ayıklama çalışma zamanı kitaplığı ile yapılandırıldığında varsayılan olarak, `abort` yordamı önce bir hata iletisi görüntüler `SIGABRT` tetiklenir. İleti gönderilir konsol modunda çalışan konsol uygulamaları için `STDERR`. Windows Masaüstü uygulamaları ve konsol uygulamaları pencereli modunda çalışan bir ileti kutusu içinde ileti görüntüler. İletinin gösterilmemesi için kullanmak [_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md) temizlemek için `_WRITE_ABORT_MSG` bayrağı. Görüntülenen ileti kullanılan çalışma zamanı ortamı sürümüne bağlıdır. Visual C++ en son sürümü kullanılarak oluşturulmuş uygulamalar için bu iletiyi benzer:  
  
 `R6010`  
  
 `- abort() has been called`  
  
 C çalışma zamanı kitaplığı önceki sürümleri bu iletiyi görüntülenen:  
  
 "`This application has requested the Runtime to terminate it in an unusual way. Please contact the application's support team for more information.`"  
  
 Program hata ayıklama modunda derlendiğinde seçenekleri ileti kutusu görüntüler **Abort**, **yeniden deneme**, veya **Yoksay**. Kullanıcı seçerse **Abort**, program hemen sonlandırır ve 3 çıkış kodu döndürür. Kullanıcı seçerse **yeniden**, bir hata ayıklayıcısı tam zamanı hata ayıklama için varsa çağrılır. Kullanıcı seçerse **Yoksay**, `abort` normal devam ettirir.  
  
 Perakende ve hata ayıklama derlemelerinde, `abort` bir durdurma sinyali işleyicisi ayarlanmış olup olmadığını denetler. Varsayılan olmayan sinyal işleyici ayarlanmışsa `abort` çağrıları `raise(SIGABRT)`. Kullanım [sinyal](../../c-runtime-library/reference/signal.md) bir durdurma sinyali işleyici işlevi ile ilişkilendirilecek işlevi `SIGABRT` sinyal. Özel eylemler gerçekleştirebilir — Örneğin, kaynakları temizlemek veya oturum bilgilerini — ve kendi hata kodu işleyici işlevindeki uygulamayla sonlanır. Hiçbir özel sinyal işleyici tanımlanmışsa `abort` yükseltmek değil `SIGABRT` sinyal.  
  
 Varsayılan olarak, masaüstü veya konsol uygulamaların olmayan hata ayıklama derlemelerinde `abort` Windows hata bildirimi mekanizması (Dr. çağırır Watson) Microsoft'a rapor hataları. Bu davranış etkin ya da çağırarak devre dışı `_set_abort_behavior` ve ayarlama veya maskeleme `_CALL_REPORTFAULT` bayrağı. Bayrağı ayarlandığında, Windows "programın düzgün çalışmayı durdurmasına neden bir şey bir sorunu." gibi metni içeren bir ileti kutusu görüntüler. Kullanıcı bir hata ayıklayıcısı ile çağrılacak seçebilir bir **hata ayıklama** düğmesini veya seçin **Programı Kapat** işletim sistemi tarafından tanımlanan bir hata kodu ile uygulama sonlandırmak için düğmesi.  
  
 Windows hata bildirimi işleyici, ardından değil çağrılırsa `abort` çağrıları [_exit](../../c-runtime-library/reference/exit-exit-exit.md) çıkış kodu 3 ve döndürür denetimine üst işleme veya işletim sistemi ile işlem sonlandırılacak. `_exit`flush akış arabellekleri veya değil yapmak `atexit` / `_onexit` işleme.  
  
 CRT hata ayıklama hakkında daha fazla bilgi için bkz: [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).  
  
 **Son Microsoft özel**  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`abort`|\<Process.h > veya \<stdlib.h >|  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Abort kullanma](../../cpp/using-abort.md)   
 [abort işlevi](../../c-language/abort-function-c.md)   
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md)   
 [Çıkış, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [Yükselt](../../c-runtime-library/reference/raise.md)   
 [Sinyal](../../c-runtime-library/reference/signal.md)   
 [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)   
 [_DEBUG](../../c-runtime-library/debug.md)   
 [_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md)