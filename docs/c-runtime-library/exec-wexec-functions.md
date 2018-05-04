---
title: _exec, _wexec işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apilocation:
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- _texecve
- texecl
- _texeclpe
- texecve
- texecv
- texeclp
- texecle
- exec
- texeclpe
- _texecvp
- _texecl
- _texecle
- wexec
- _exec
- _texeclp
- _texecvpe
- texecvpe
- _texecv
- _wexec
dev_langs:
- C++
helpviewer_keywords:
- _texecle function
- _texecv function
- texeclpe function
- texecle function
- _texecl function
- texecv function
- _texeclp function
- _texecve function
- texecl function
- texecve function
- exec function
- texeclp function
- texecvp function
- texecvpe function
- processes, executing new
- _texecvp function
- _texeclpe function
- _wexec functions
- wexec functions
- _exec function
- _texecvpe function
ms.assetid: a261df93-206a-4fdc-b8ac-66aa7db83bc6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ef98749c094165cb7cdff9f20370a55dfdaaa3a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="exec-wexec-functions"></a>_exec, _wexec İşlevleri
Bu ailedeki her işlevi yükler ve yeni bir işlem çalıştırır:  
  
|||  
|-|-|  
|[_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)|[_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)|  
|[_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)|[_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)|  
|[_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|[_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|  
|[_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|[_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|  
  
 İşlev adı sonunda harf değişim belirler.  
  
|_exec işlevi soneki|Açıklama|  
|----------------------------|-----------------|  
|`e`|`envp`, dizi işaretçileri ortam ayarları için yeni işlemin geçirilir.|  
|`l`|Komut satırı bağımsız değişkenleri için ayrı ayrı geçirilir `_exec` işlevi. Genellikle, yeni işlem için parametre sayısı önceden bilinen olduğunda kullanılır.|  
|`p`|`PATH` ortam değişkeni yürütmek için dosyayı bulmak için kullanılır.|  
|`v`|`argv`, dizi için komut satırı bağımsız değişkenleri için işaretçileri, geçirilen `_exec`. Genellikle, yeni işlem için parametre sayısı değişken olduğunda kullanılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Her `_exec` işlevi yükler ve yeni bir işlem yürütür. Tüm `_exec` işlevlerini kullanan aynı işletim sistemi işlevi ([CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms682425.aspx)). `_exec` İşlevler şu anda kullanımda birden çok baytlı kod sayfasına göre çok baytlı karakter sıralarının algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak işler. `_wexec` İşlevlerdir joker karakter sürümlerini `_exec` işlevleri. `_wexec` İşlevleri aynı şekilde davranır kendi `_exec` ailesi ortaklarınıza dışında çok baytlı karakter dizeleri işlemez.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_texecl`|`_execl`|`_execl`|`_wexecl`|  
|`_texecle`|`_execle`|`_execle`|`_wexecle`|  
|`_texeclp`|`_execlp`|`_execlp`|`_wexeclp`|  
|`_texeclpe`|`_execlpe`|`_execlpe`|`_wexeclpe`|  
|`_texecv`|`_execv`|`_execv`|`_wexecv`|  
|`_texecve`|`_execve`|`_execve`|`_wexecve`|  
|`_texecvp`|`_execvp`|`_execvp`|`_wexecvp`|  
|`_texecvpe`|`_execvpe`|`_execvpe`|`_wexecvpe`|  
  
 `cmdname` Parametresi yeni işlem yürütülebilir dosyaya belirtir. Bir tam yolu (kök), bir kısmi yolundan (geçerli çalışma dizini) veya bir dosya adı belirtebilirsiniz. Varsa `cmdname` bir dosya adı uzantısı yok veya bir nokta (.) ile bitmez `_exec` işlev adlandırılmış dosya arar. Arama başarısız olursa, aynı taban adına .com dosya adı uzantısına sahip, ardından .exe, .bat ve .cmd dosya adı uzantıları ile çalışır. Varsa `cmdname` bir dosya adı uzantısına sahip yalnızca bir uzantı aramada kullanılır. Varsa `cmdname` bir nokta ile biten `_exec` işlevi arar `cmdname` hiçbir dosya adı uzantısına sahip. `_execlp`, `_execlpe`, `_execvp`, ve `_execvpe` arama `cmdname` (aynı yordamları kullanarak) tarafından belirtilen dizinlerde `PATH` ortam değişkeni. Varsa `cmdname` sürücü belirleyici veya herhangi bir eğik çizgi (diğer bir deyişle, göreli bir yol ise) içeren, `_exec` çağrısı için yalnızca belirtilen dosya arar; yolu yapılmaz.  
  
 Parametreleri, parametre olarak karakter dizeleri için bir veya daha fazla işaretçileri vererek yeni işlem geçirilir `_exec` çağırın. Bu karakter dizelerini yeni işlem için parametre listesi oluşturur. Devralınan ortam ayarları ve yeni işlem için parametre listesi oluşturuluyor dizeleri toplam uzunluğu 32 kilobaytı aşmamalıdır. Her bir dize sonlandırma null karakteri ('\0') sayıma dahil değildir, ancak (otomatik olarak eklenen parametreleri ayırmak için) boşluk karakterleri kabul edilir.  
  
> [!NOTE]
>  Dizelerde katıştırılmış boşluklar beklenmeyen davranışlara neden olabilir; Örneğin, geçirme `_exec` dize `"hi there"` iki bağımsız değişkeni alma yeni işleminde sonuçlanır `"hi"` ve `"there"`. Hedefi adlı bir dosyayı açan yeni işlem için ise "Merhaba var.", işlem başarısız olur. Bu dize tırnak içine almak kaçının: `"\"hi there\""`.  
  
> [!IMPORTANT]
>  Kullanıcı girişini geçmeyin `_exec` açıkça içeriğini Denetlemeden. `_exec` Çağrı sonuçlanır [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms682425.aspx) şekilde adları, olası güvenlik açıklarını açabilir nitelenmemiş yol göz önünde bulundurun.  
  
 `_exec` İşlevleri parametrelerini doğrulayın. Parametre null işaretçiler beklenir, boş dizeler veya çıkarılırsa `_exec` işlevleri çağırma geçersiz parametre işleyicisi açıklandığı gibi [parametre doğrulaması](../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL` ve -1 döndürür. Yeni bir işlem yürütülür.  
  
 Bağımsız değişken işaretçileri ayrı parametre olarak geçirilebilir (içinde `_execl`, `_execle`, `_execlp`, ve `_execlpe`) veya bir dizi işaretçileri olarak (içinde `_execv`, `_execve`, `_execvp`, ve `_execvpe`). En az bir parametre `arg0`, yeni işlemin; geçirilmelidir Bu parametre `argv`[0] yeni işlemin. Genellikle, bu parametre bir kopyasıdır `cmdname`. (Farklı bir değer hata üretmez.)  
  
 `_execl`, `_execle`, `_execlp`, Ve `_execlpe` çağrıları parametrelerin sayısı önceden bilindiğinde genellikle kullanılır. Parametre `arg0` genellikle gösteren bir işaretçidir `cmdname`. Parametreleri `arg1` aracılığıyla `argn` noktası yeni parametre listesi oluşturuluyor karakter dizeleri. Null işaretçinin izlemelisiniz `argn` parametre listesinin sonuna işaretlenecek.  
  
 `_execv`, `_execve`, `_execvp`, Ve `_execvpe` çağrıları kullanışlı ne zaman yeni işlem için parametre sayısı değişkendir. Parametreleri işaretçiler bir dizisi olarak geçirilir `argv`. Parametre `argv`[0] genellikle gösteren bir işaretçidir `cmdname`. Parametreleri `argv`[1] aracılığıyla `argv`[`n`] noktası yeni parametre listesi oluşturuluyor karakter dizeleri. Parametre `argv`[`n`+ 1] olmalıdır bir `NULL` parametre listesinin sonuna işaretlemek için işaretçi.  
  
 Açık olan dosyalar bir `_exec` çağrısı yapılan yeni işlemde açık kalır. İçinde `_execl`, `_execlp`, `_execv`, ve `_execvp` çağrıları, yeni işlem çağırma işleminin ortamı devralır. `_execle`, `_execlpe`, `_execve`, ve `_execvpe` çağrıları alter ortam yeni işlem için ortam Ayarları'nda listesini geçirerek `envp` parametresi. `envp` karakter işaretçileri (dışında son öğesi) her öğesinin null ile sonlandırılmış bir dizeye işaret dizisi bir ortam değişkeni tanımlama. Bu tür bir dize genellikle form sahip `NAME` = `value` nerede `NAME` bir ortam değişkeni adı ve `value` değişken ayarlanmış dize değeridir. (Unutmayın `value` çift tırnak işaretleri içine alınmamış.) Son öğenin `envp` dizi olmalıdır `NULL`. Zaman `envp` kendisi `NULL`, yeni işlem çağırma işleminin ortam ayarlarını devralır.  
  
 Biri ile yürütülebilir bir program `_exec` programın .exe dosya üstbilgisi maksimum ayırma alanında 0xFFFFH varsayılan değerine ayarlandıysa gibi işlevler belleğe her zaman yüklenir.  
  
 `_exec` Çağrıları açık dosyaların çeviri modları korumak değil. Yeni işlem arama işlemden devralınan dosyaları kullanmanız gerekiyorsa kullanın [_setmode](../c-runtime-library/reference/setmode.md) istenen moduna bu dosyaların çeviri modu ayarlamak için yordamı. Açıkça flush gerekir (kullanarak `fflush` veya `_flushall`) veya akış önce kapatın `_exec` işlev çağrısı. Sinyal ayarları korunmaz yapılan çağrılar tarafından oluşturulan yeni işlemlerde `_exec` yordamları. Sinyal ayarları varsayılan yeni işlem sıfırlanır.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_args.c  
// Illustrates the following variables used for accessing  
// command-line arguments and environment variables:  
// argc  argv  envp  
// This program will be executed by crt_exec which follows.  
  
#include <stdio.h>  
  
int main( int argc,  // Number of strings in array argv  
 char *argv[],       // Array of command-line argument strings  
 char **envp )       // Array of environment variable strings  
{  
    int count;  
  
    // Display each command-line argument.  
    printf( "\nCommand-line arguments:\n" );  
    for( count = 0; count < argc; count++ )  
        printf( "  argv[%d]   %s\n", count, argv[count] );  
  
    // Display each environment variable.   
    printf( "\nEnvironment variables:\n" );  
    while( *envp != NULL )  
        printf( "  %s\n", *(envp++) );  
  
    return;  
}  
```  
  
 Crt_args.exe çalıştırmak için aşağıdaki programı çalıştır:  
  
```  
// crt_exec.c  
// Illustrates the different versions of exec, including  
//      _execl          _execle          _execlp          _execlpe  
//      _execv          _execve          _execvp          _execvpe  
//  
// Although CRT_EXEC.C can exec any program, you can verify how   
// different versions handle arguments and environment by   
// compiling and specifying the sample program CRT_ARGS.C. See   
// "_spawn, _wspawn Functions" for examples of the similar spawn   
// functions.  
  
#include <stdio.h>  
#include <conio.h>  
#include <process.h>  
  
char *my_env[] =     // Environment for exec?e  
{  
   "THIS=environment will be",  
   "PASSED=to new process by",  
   "the EXEC=functions",  
   NULL  
};  
  
int main( int ac, char* av[] )  
{  
   char *args[4];  
   int ch;  
   if( ac != 3 ){  
      fprintf( stderr, "Usage: %s <program> <number (1-8)>\n", av[0] );  
      return;  
   }  
  
   // Arguments for _execv?   
   args[0] = av[1];  
   args[1] = "exec??";  
   args[2] = "two";  
   args[3] = NULL;  
  
   switch( atoi( av[2] ) )  
   {  
   case 1:  
      _execl( av[1], av[1], "_execl", "two", NULL );  
      break;  
   case 2:  
      _execle( av[1], av[1], "_execle", "two", NULL, my_env );  
      break;  
   case 3:  
      _execlp( av[1], av[1], "_execlp", "two", NULL );  
      break;  
   case 4:  
      _execlpe( av[1], av[1], "_execlpe", "two", NULL, my_env );  
      break;  
   case 5:  
      _execv( av[1], args );  
      break;  
   case 6:  
      _execve( av[1], args, my_env );  
      break;  
   case 7:  
      _execvp( av[1], args );  
      break;  
   case 8:  
      _execvpe( av[1], args, my_env );  
      break;  
   default:  
      break;  
   }  
  
   // This point is reached only if exec fails.   
   printf( "\nProcess was not execed." );  
   exit( 0 );  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
 **Başlık:** process.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../c-runtime-library/process-and-environment-control.md)   
 [Durdurma](../c-runtime-library/reference/abort.md)   
 [atexit](../c-runtime-library/reference/atexit.md)   
 [Çıkış, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn işlevleri](../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../c-runtime-library/reference/system-wsystem.md)