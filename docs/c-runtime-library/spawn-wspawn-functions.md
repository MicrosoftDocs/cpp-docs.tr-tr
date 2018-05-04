---
title: _spawn, _wspawn işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apilocation:
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- _spawn
- _tspawnlp
- _tspawnlpe
- _tspawnve
- _tspawnvp
- _tspawnvpe
- _tspawnl
- spawn
- _tspawnv
- _tspawnle
- wspawn
dev_langs:
- C++
helpviewer_keywords:
- _tspawnve function
- _spawn functions
- _tspawnlpe function
- tspawnvpe function
- processes, creating
- tspawnve function
- _tspawnvp function
- spawn functions
- tspawnl function
- tspawnlp function
- _tspawnvpe function
- _tspawnl function
- tspawnvp function
- tspawnv function
- processes, executing new
- _tspawnv function
- tspawnle function
- process creation
- _tspawnlp function
- tspawnlpe function
- _tspawnle function
ms.assetid: bb47c703-5216-4e09-8023-8cf25bbf2cf9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 298e2a1abddc477e406bca17bce04999c6e09415
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="spawn-wspawn-functions"></a>_spawn, _wspawn İşlevleri
Her biri `_spawn` işlevleri oluşturur ve yeni bir işlem çalıştırır:  
  
|||  
|-|-|  
|[_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|[_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|  
|[_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|[_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|  
|[_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|[_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|  
|[_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|[_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|  
  
 İşlev adı sonunda harf değişim belirler.  
  
 `e`  
 `envp`, dizi işaretçileri ortam ayarları için yeni işlemin geçirilir.  
  
 `l`  
 Komut satırı bağımsız değişkenleri için ayrı ayrı geçirilir `_spawn` işlevi. Yeni bir işlem için parametre sayısı önceden bilindiğinde bu soneki genellikle kullanılır.  
  
 `p`  
 `PATH` ortam değişkeni yürütmek için dosyayı bulmak için kullanılır.  
  
 `v`  
 `argv`, dizi için komut satırı bağımsız değişkenleri için işaretçileri, geçirilen `_spawn` işlevi. Yeni bir işlem için parametre sayısı değişken olduğunda bu soneki genellikle kullanılır.  
  
## <a name="remarks"></a>Açıklamalar  
 `_spawn` İşlevleri her oluşturma ve yeni bir işlem yürütme. Bunlar otomatik olarak şu anda kullanımda birden çok baytlı kod sayfasına göre çok baytlı karakter sıralarının algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde işler. `_wspawn` İşlevlerdir joker karakter sürümlerini `_spawn` işlevleri; çok baytlı karakter dizeleri işlemez. Aksi takdirde, `_wspawn` işlevleri aynı şekilde davranır kendi `_spawn` ortaklarınıza.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tspawnl`|`_spawnl`|`_spawnl`|`_wspawnl`|  
|`_tspawnle`|`_spawnle`|`_spawnle`|`_wspawnle`|  
|`_tspawnlp`|`_spawnlp`|`_spawnlp`|`_wspawnlp`|  
|`_tspawnlpe`|`_spawnlpe`|`_spawnlpe`|`_wspawnlpe`|  
|`_tspawnv`|`_spawnv`|`_spawnv`|`_wspawnv`|  
|`_tspawnve`|`_spawnve`|`_spawnve`|`_wspawnve`|  
|`_tspawnvp`|`_spawnvp`|`_spawnvp`|`_wspawnvp`|  
|`_tspawnvpe`|`_spawnvpe`|`_spawnvpe`|`_wspawnvpe`|  
  
 Yeterli bellek yükleme ve yeni işlem yürütme için kullanılabilir olmalıdır. `mode` Bağımsız değişkeni belirler ve önce sırasında arama işlemi tarafından gerçekleştirilecek eylemi `_spawn`. Aşağıdaki değerleri `mode` Process.h içinde tanımlanır:  
  
 `_P_OVERLAY`  
 Yer paylaşımları arama bir arama işlemi yok etme sahip yeni bir işlem, işlem (aynı efekt olarak `_exec` çağrıları).  
  
 `_P_WAIT`  
 Yeni işlem yürütme işlemi tamamlanana kadar çağıran iş parçacığı askıya alır (zaman uyumlu `_spawn`).  
  
 `_P_NOWAIT` Veya `_P_NOWAITO`  
 Eşzamanlı olarak yeni işlem çağırma işlemi yürütmeye devam eder (zaman uyumsuz `_spawn`).  
  
 `_P_DETACH`  
 Arama işlemi yürütmeye devam eder; Yeni işlem konsolunu veya klavye, hiçbir erişim arka planda çalıştırılır. Çağrılar `_cwait` karşı yeni işlem başarısız (zaman uyumsuz `_spawn`).  
  
 `cmdname` Bağımsız değişken bir tam yolu (kök), bir kısmi yolundan (geçerli çalışma dizini) veya yalnızca dosya adını belirtebilirsiniz ve yeni işlem olarak çalıştırılan dosyayı belirtir. Varsa `cmdname` bir dosya adı uzantısı yok veya bir nokta (.) ile bitmez `_spawn` işlevi ilk çalıştığında .com dosya adı uzantısı ve .exe dosya adı uzantısı, .bat dosya adı uzantısı ve son olarak .cmd dosya adı uzantısı.  
  
 Varsa `cmdname` uzantısı kullanılır bir dosya adı uzantısı, yalnızca sahiptir. Varsa `cmdname` bir nokta ile biten `_spawn` çağırmak için aramaları `cmdname` hiçbir dosya adı uzantısına sahip. `_spawnlp`, `_spawnlpe`, `_spawnvp`, Ve `_spawnvpe` işlevleri aramak için `cmdname` (aynı yordamları kullanarak) tarafından belirtilen dizinlerde `PATH` ortam değişkeni.  
  
 Varsa `cmdname` sürücü belirleyici veya herhangi bir eğik çizgi (diğer bir deyişle, göreli bir yol ise) içeren, `_spawn` çağrısı için yalnızca belirtilen dosya arar; hiçbir yolu arama yapılır.  
  
 Geçmişte, bunlardan bazıları işlevleri kümesi `errno` sıfır üzerinde başarılı durumuna; şu anki davranışı bırakmaktır `errno` C standardı belirtildiği gibi başarılı olduğu gibi kalmıştır. Eski davranışını benzetmek gerekiyorsa, ayarlamak `errno` bu işlevleri çağırma hemen önce sıfır.  
  
> [!NOTE]
>  Uygun bir katmana başlatma ve sonlandırma emin olmak için kullanmayın `setjmp` veya `longjmp` girin veya bir katmana yordamı ayrılma işlevi.  
  
## <a name="arguments-for-the-spawned-process"></a>Oluşturulan işlemi için bağımsız değişkenler  
 Bağımsız değişkenler yeni sürecine iletmek için bağımsız değişken olarak karakter dizeleri için bir veya daha fazla işaretçileri vermek `_spawn` çağırın. Bu karakter dizelerini oluşturulan işlemi için bağımsız değişken listesi oluşturur. Yeni işlem için bağımsız değişken listesi oluşturuluyor dizeleri toplam uzunluğu 1024 baytı aşmamalıdır. Her dize sonlandırma null karakteri ('\0') sayıma dahil değildir, ancak boşluk karakterleri (bağımsız değişkenler ayırmak için otomatik olarak eklenir) dahil edilir.  
  
> [!NOTE]
>  Dizelerde katıştırılmış boşluklar beklenmeyen davranışlara neden olabilir; Örneğin, geçirme `_spawn` dize `"hi there"` iki bağımsız değişkeni alma yeni işleminde sonuçlanır `"hi"` ve `"there"`. Hedefi adlı bir dosyayı açan yeni işlem için ise "Merhaba var.", işlem başarısız olur. Bu dize tırnak içine almak kaçının: `"\"hi there\""`.  
  
> [!IMPORTANT]
>  Kullanıcı girişini geçmeyin `_spawn` açıkça içeriğini Denetlemeden. `_spawn` Çağrı sonuçlanır [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms682425) şekilde adları, olası güvenlik açıklarını açabilir nitelenmemiş yol göz önünde bulundurun.  
  
 Bağımsız değişken işaretçileri olarak ayrı bağımsız değişkenler geçirebilirsiniz (içinde `_spawnl`, `_spawnle`, `_spawnlp`, ve `_spawnlpe`) veya bir dizi işaretçileri olarak (içinde `_spawnv`, `_spawnve`, `_spawnvp`, ve `_spawnvpe`). En az bir değişken geçmelidir `arg0` veya `argv`[0], oluşturulan işlemi için. Komut satırında yazarsınız kurala göre bu bağımsız değişken programın adını aynıdır. Farklı bir değer hata üretmez.  
  
 `_spawnl`, `_spawnle`, `_spawnlp`, Ve `_spawnlpe` çağrıları genellikle burada bağımsız değişken sayısı bilinen önceden durumlarda kullanılır. `arg0` Bağımsız değişkeni genellikle bir işaretçidir `cmdname`. Bağımsız değişkenler `arg1` aracılığıyla `argn` yeni bağımsız değişken listesi oluşturuluyor karakter dizelerini işaretçileridir. Aşağıdaki `argn`, olmalıdır bir `NULL` bağımsız değişken listesinin sonuna işaretlemek için işaretçi.  
  
 `_spawnv`, `_spawnve`, `_spawnvp`, Ve `_spawnvpe` çağrıları, değişken sayıda bağımsız değişken için yeni işlem olduğunda faydalıdır. Bağımsız değişkenler işaretçiler bir dizisi olarak geçirilir `argv` *.* Bağımsız değişken `argv`[0] genellikle bir yol için bir işaretçi gerçek modda program adı için korumalı modda mı ve `argv`[1] aracılığıyla `argv`[`n`] için ilgili yeni bağımsız değişken listesi oluşturuluyor karakter dizeleri. Bağımsız değişken `argv`[`n` + 1] olmalıdır bir `NULL` bağımsız değişken listesinin sonuna işaretlemek için işaretçi.  
  
## <a name="environment-of-the-spawned-process"></a>Oluşturulan işlemi ortamı  
 Açık olan dosyalar bir `_spawn` çağrısı yapılan yeni işlemde açık kalır. İçinde `_spawnl`, `_spawnlp`, `_spawnv`, ve `_spawnvp` çağrıları, yeni işlem çağırma işleminin ortamı devralır. Kullanabileceğiniz `_spawnle`, `_spawnlpe`, `_spawnve`, ve `_spawnvpe` ortam yeni işlem için ortam Ayarları'nda listesini geçirerek alter çağrıları `envp` bağımsız değişkeni. Bağımsız değişken `envp` her öğesinin (dışında son öğesi) gösteren bir ortam değişkeni tanımlama null ile sonlandırılmış bir dizeye karakter işaretçileri dizisidir. Bu tür bir dize genellikle form sahip `NAME` = `value` nerede `NAME` bir ortam değişkeni adı ve `value` değişken ayarlanmış dize değeridir. (Unutmayın `value` çift tırnak işaretleri içine alınmamış.) Son öğenin `envp` dizi olmalıdır `NULL`. Zaman `envp` kendisi `NULL`, oluşturulan işlemi üst işleminin ortam ayarlarını devralır.  
  
 `_spawn` İşlevleri yeni işleme çeviri modu dahil olmak üzere açık dosyalar hakkındaki tüm bilgileri iletebilir. Bu bilgi, gerçek modu üzerinden geçirilen `C_FILE_INFO` ortamında girişi. Başlangıç kodu normalde bu girişi işler ve ortamından siler. Ancak, bir `_spawn` işlevi olarak çoğaltılır C olmayan işlemi, bu girdi ortamda kalır. Ortam bilgileri gerçek modda ikili biçimde geçtiğinden ortamı yazdırma bu girişi tanımı dizesinde grafik karakterlerini gösterir. Normal işlemler üzerinde herhangi bir etkisi olmamalıdır. Korumalı modda ortamı bilgileri metin biçiminde geçirilir ve bu nedenle hiçbir grafik karakter içerir.  
  
 Açıkça flush gerekir (kullanarak `fflush` veya `_flushall`) veya akış çağırmadan önce kapatın bir `_spawn` işlevi.  
  
 Yapılan çağrılar tarafından oluşturulan yeni işlemleri `_spawn` yordamları sinyali ayarlarını korumak değil. Bunun yerine, oluşturulan işlemi sinyali ayarlarını varsayılan ayarlarına sıfırlar.  
  
## <a name="redirecting-output"></a>Çıktı yeniden yönlendirme  
 Aradığınız varsa `_spawn` DLL veya bir GUI uygulamasından ve bir kanala çıkışı yönlendirmek istiyorsanız, iki seçeneğiniz vardır:  
  
-   Bir kanal oluşturmak için Win32 API kullanın'ı çağırın [AllocConsole](http://msdn.microsoft.com/library/windows/desktop/ms681944), başlangıç yapısı ve çağrı tanıtıcı değerleri ayarlamak [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms682425).  
  
-   Çağrı [_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md) , bir kanal oluşturmak ve uygulamayı kullanarak çağırma **cmd.exe /c** (veya **command.exe /c**).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_spawn.c  
// This program accepts a number in the range  
// 1-8 from the command line. Based on the number it receives,  
// it executes one of the eight different procedures that  
// spawn the process named child. For some of these procedures,  
// the CHILD.EXE file must be in the same directory; for  
// others, it only has to be in the same path.  
//  
  
#include <stdio.h>  
#include <process.h>  
  
char *my_env[] =  
{  
   "THIS=environment will be",  
   "PASSED=to child.exe by the",  
   "_SPAWNLE=and",  
   "_SPAWNLPE=and",  
   "_SPAWNVE=and",  
   "_SPAWNVPE=functions",  
   NULL  
};  
  
int main( int argc, char *argv[] )  
{  
   char *args[4];  
  
   // Set up parameters to be sent:   
   args[0] = "child";  
   args[1] = "spawn??";  
   args[2] = "two";  
   args[3] = NULL;  
  
   if (argc <= 2)  
   {  
      printf( "SYNTAX: SPAWN <1-8> <childprogram>\n" );  
      exit( 1 );  
   }  
  
   switch (argv[1][0])   // Based on first letter of argument   
   {  
   case '1':  
      _spawnl( _P_WAIT, argv[2], argv[2], "_spawnl", "two", NULL );  
      break;  
   case '2':  
      _spawnle( _P_WAIT, argv[2], argv[2], "_spawnle", "two",   
               NULL, my_env );  
      break;  
   case '3':  
      _spawnlp( _P_WAIT, argv[2], argv[2], "_spawnlp", "two", NULL );  
      break;  
   case '4':  
      _spawnlpe( _P_WAIT, argv[2], argv[2], "_spawnlpe", "two",   
                NULL, my_env );  
      break;  
   case '5':  
      _spawnv( _P_OVERLAY, argv[2], args );  
      break;  
   case '6':  
      _spawnve( _P_OVERLAY, argv[2], args, my_env );  
      break;  
   case '7':  
      _spawnvp( _P_OVERLAY, argv[2], args );  
      break;  
   case '8':  
      _spawnvpe( _P_OVERLAY, argv[2], args, my_env );  
      break;  
   default:  
      printf( "SYNTAX: SPAWN <1-8> <childprogram>\n" );  
      exit( 1 );  
   }  
   printf( "from SPAWN!\n" );  
}  
```  
  
```Output  
child process output  
from SPAWN!  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../c-runtime-library/process-and-environment-control.md)   
 [Durdurma](../c-runtime-library/reference/abort.md)   
 [atexit](../c-runtime-library/reference/atexit.md)   
 [_exec, _wexec işlevleri](../c-runtime-library/exec-wexec-functions.md)   
 [Çıkış, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../c-runtime-library/reference/flushall.md)   
 [_getmbcp](../c-runtime-library/reference/getmbcp.md)   
 [_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)   
 [_setmbcp](../c-runtime-library/reference/setmbcp.md)   
 [system, _wsystem](../c-runtime-library/reference/system-wsystem.md)