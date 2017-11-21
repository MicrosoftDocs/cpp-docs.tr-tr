---
title: "Çıkış, _Exit, _exit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _exit
- exit
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
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
dev_langs: C++
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
ms.assetid: b1501fa6-27c2-478c-9e93-cc4fd802a01f
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f68ef6938c1f42ccde300838915292c5abe36af
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="exit-exit-exit"></a>Çıkış, _Exit, _exit
Arama işlemi sonlandırır. `exit` İşlevi sonlandırır, temizleme sonrasında; `_exit` ve `_Exit` hemen sonlandır.  
  
> [!NOTE]
>  Bu yöntem, bir evrensel Windows Platformu (UWP) uygulamasını kapatmak için kullanmayın veya [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulama, dışındaki test veya senaryoları hata ayıklama. Kapatmak için programlı veya UI yolu bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulama izin verilmez. Windows 8 ve 8.1 uygulamaları hakkında daha fazla bilgi için bkz: [uygulama yaşam döngüsü](http://go.microsoft.com/fwlink/?LinkId=262853). Windows 10 uygulamaları hakkında daha fazla bilgi için bkz: [nasıl yapılır kılavuzları için Windows 10 uygulamaları](http://go.microsoft.com/fwlink/p/?linkid=619133).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void exit(   
   int const status   
);  
void _Exit(   
   int const status   
);  
void _exit(   
   int const status   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `status`  
 Durum kodu çıkın.  
  
## <a name="remarks"></a>Açıklamalar  
 `exit`, `_Exit` Ve `_exit` işlevleri çağırma işlemi sonlandırılacak. `exit` İşlevi çağırır Yıkıcılar iş parçacığı yerel nesneler için daha sonra çağırır — son olarak ilk çıkar (LIFO) sırayla — tarafından kaydedilen işlevleri `atexit` ve `_onexit`ve işlem sona erdirmeden önce tüm dosya arabelleklerini alır. `_Exit` Ve `_exit` işlevleri sonlandırma işlemi iş parçacığı yerel nesneleri yok etme veya işlemeden `atexit` veya `_onexit` işlevler ve akış arabellekleri temizleme olmadan.  
  
 Ancak `exit`, `_Exit` ve `_exit` çağrıları değer'de bir değer döndürmeyen `status` işlemi çıktıktan sonra varsa ana bilgisayar ortamının veya bekleme çağırma işlemi, kullanılabilir hale getirilir. Genellikle, çağıran kümeleri `status` değer normal bir çıkış göstermek için 0 veya bir hata göstermek için başka bir değer. `status` Değeri işletim sistemi toplu komutuna kullanılabilir `ERRORLEVEL` ve iki sabitlerden biri tarafından temsil edilen: `EXIT_SUCCESS`, 0 değerini temsil eder veya `EXIT_FAILURE`, 1 değerini temsil eder.  
  
 `exit`, `_Exit`, `_exit`, `quick_exit`, `_cexit`, Ve `_c_exit` işlevleri gibi davranır.  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|`exit`|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının için sağlanan durum kodu sağlar.|  
|`_Exit`|En az C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının için sağlanan durum kodu sağlar.|  
|`_exit`|En az C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının için sağlanan durum kodu sağlar.|  
|`quick_exit`|Hızlı C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamının için sağlanan durum kodu sağlar.|  
|`_cexit`|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döndürür. İşlemi Sonlandır değil.|  
|`_c_exit`|En az C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döndürür. İşlemi Sonlandır değil.|  
  
Çağırdığınızda `exit`, `_Exit` veya `_exit` işlev çağrısı sırada mevcut geçici veya otomatik nesneleri için Yıkıcılar çağrılır değil. Tanımlı bir işlevde statik olmayan yerel bir nesne bir otomatik nesnesidir. Geçici bir nesne gibi bir işlev çağrısı tarafından döndürülen değer derleyici tarafından oluşturulan nesnedir. Arama yapmadan önce bir otomatik nesne yok etmek için `exit`, `_Exit`, veya `_exit`, açıkça yıkıcı nesne için aşağıda gösterildiği gibi çağırın:  
  
```cpp 
void last_fn() {} 
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);  
}
```  
  
Kullanmayın `DLL_PROCESS_ATTACH` çağırmak için `exit` gelen `DllMain`. Çıkmak için `DLLMain` işlev, dönüş `FALSE` gelen `DLL_PROCESS_ATTACH`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`exit`, `_Exit`, `_exit`|\<Process.h > veya \<stdlib.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_exit.c  
// This program returns an exit code of 1. The  
// error code could be tested in a batch file.  
  
#include <stdlib.h>  
  
int main( void )  
{  
   exit( 1 );  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [durdurma](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_cexit, _c_exit](../../c-runtime-library/reference/cexit-c-exit.md)   
 [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [quick_exit](../../c-runtime-library/reference/quick-exit1.md)   
 [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)   
 [Sistem, _wsystem](../../c-runtime-library/reference/system-wsystem.md)