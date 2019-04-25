---
title: _exec, _wexec İşlevleri
ms.date: 11/04/2016
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
ms.openlocfilehash: 72300f754015e54daf14863ca2ae677bde8f7d1a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62289695"
---
# <a name="exec-wexec-functions"></a>_exec, _wexec İşlevleri

Bu iş ailesindeki her işlev, yükler ve yeni bir işlem yürütür:

|||
|-|-|
|[_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)|[_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)|
|[_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)|[_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)|
|[_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|[_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|
|[_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|[_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|

İşlev adının sonuna bir harf çeşitlemesini belirler.

|_exec işlevi soneki|Açıklama|
|----------------------------|-----------------|
|`e`|`envp`, dizi işaretçileri ortam ayarlarına, yeni işlemin geçirilir.|
|`l`|Komut satırı bağımsız değişkenleri için ayrı ayrı geçirilir `_exec` işlevi. Genellikle, yeni işlem için parametre sayısı önceden bilindiğinde kullanılır.|
|`p`|`PATH` ortam değişkeni, yürütülecek dosyayı bulmak için kullanılır.|
|`v`|`argv`, dizi işaretçileri komut satırı bağımsız değişkenleri, geçirilen `_exec`. Genellikle, yeni işlem için parametre sayısı değişken olduğunda kullanılır.|

## <a name="remarks"></a>Açıklamalar

Her `_exec` işlevi yükler ve yeni bir işlem yürütür. Tüm `_exec` işlevleri aynı işletim sistemi işlevini kullanın ([CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa)). `_exec` İşlevleri çok baytlı karakter sıralarını şu anda çok baytlı kod sayfasına göre algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak işler. `_wexec` İşlevleri olan geniş karakter sürümleri `_exec` işlevleri. `_wexec` İşlevler öğesine aynı şekilde davranır, `_exec` ailesi ortaklarınıza hariç, çok baytlı karakter dizelerini işlemez.

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

`cmdname` Parametresi, yeni bir işlem olarak yürütülecek dosyayı belirtir. Bir tam yolu (kök), (konumundan geçerli çalışma dizini) kısmi bir yol veya dosya adı belirtebilirsiniz. Varsa `cmdname` bir dosya adı uzantısına sahip değil veya bir nokta (.) ile bitmiyor `_exec` işlev adlı dosyayı arar. Arama başarısız olursa, aynı temel ada .com dosya adı uzantısına sahip, ardından .exe, .bat ve .cmd dosya adı uzantıları ile çalışır. Varsa `cmdname` bir dosya adı uzantısına sahip yalnızca bir uzantı aramaya kullanılır. Varsa `cmdname` nokta ile biten `_exec` işlevi arar `cmdname` hiçbir dosya adı uzantısına sahip. `_execlp`, `_execlpe`, `_execvp`, ve `_execvpe` arama `cmdname` (aynı yordamları kullanarak) tarafından belirtilen dizinlerde `PATH` ortam değişkeni. Varsa `cmdname` (diğer bir deyişle, göreli bir yol ise), bir sürücü tanımlayıcısı veya herhangi bir eğik çizgi içeren, `_exec` çağrı için yalnızca belirtilen dosyasını arar; yolu yapılmaz.

Parametreler, parametre olarak karakter dizeleri için bir veya daha fazla işaretçiden vererek yeni işleme geçirilir `_exec` çağırın. Bu karakter dizeleri yeni işlem için parametre listesi oluşturur. Devralınan ortam ayarlarını ve yeni işlem için parametre listesi oluşturuluyor dizelerinin toplam uzunluğu 32 kilobaytı aşamaz. Sondaki boş karakter ('\0') için her dizeye sayı yer almaz, ancak boşluk karakterleri (parametreleri ayırmak için otomatik olarak eklenir) sayılır.

> [!NOTE]
>  Dizeler gömülü boşluklar beklenmeyen davranışlara neden olabilir; Örneğin, geçirme `_exec` dize `"hi there"` iki bağımsız değişkeni, alma yeni işleminde sonuçlanır `"hi"` ve `"there"`. Amaç adlı bir dosyayı açma yeni işlem sahip ise "Merhaba yok", işlem başarısız olur. Bu dize Alıntısı tarafından kaçının: `"\"hi there\""`.

> [!IMPORTANT]
>  Kullanıcı girişi için geçmeyin `_exec` açıkça içeriğini Denetlemeden. `_exec` bir çağrı sonuçlanır [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa) şekilde nitelenmemiş yol adları için olası güvenlik açıklarını müşteri adayı göz önünde bulundurun.

`_exec` İşlevleri kendi parametrelerini doğrular. Parametreleri null karmaşık işaretçilere beklenir, boş dizeler ya da yoksayılır, `_exec` işlevleri açıklandığı gibi geçersiz parametre işleyicisi çağırır [Parameter Validation](../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi `errno` için `EINVAL` ve -1 döndürür. Yeni bir işlem yürütülmedi.

Bağımsız değişken işaretçileri ayrı bir parametre olarak geçirilebilir (içinde `_execl`, `_execle`, `_execlp`, ve `_execlpe`) veya bir işaretçiler dizisi olarak (içinde `_execv`, `_execve`, `_execvp`, ve `_execvpe`). En az bir parametre `arg0`, yeni işlemin; geçirilmelidir Bu parametre `argv`[0] yeni bir işlem. Genellikle, bu parametre bir kopyasıdır `cmdname`. (Farklı bir değer, bir hata oluşturmaz.)

`_execl`, `_execle`, `_execlp`, Ve `_execlpe` çağrıları parametre sayısı önceden bilindiğinde genellikle kullanılır. Parametre `arg0` genellikle işaretçisidir `cmdname`. Parametreleri `arg1` aracılığıyla `argn` yeni parametre listesini oluşturan karakter dizelerine işaretçilerdir için gelin. Bir null işaretçi izlemelidir `argn` parametre listesinin sonunu işaretlemek için.

`_execv`, `_execve`, `_execvp`, Ve `_execvpe` çağrılarıdır kullanışlı ne zaman yeni işlem için parametre sayısı değişkenidir. Parametreler için işaretçiler, bir dizi olarak geçirilir `argv`. Parametre `argv`[0] genellikle işaretçisidir `cmdname`. Parametreleri `argv`[1] aracılığıyla `argv`[`n`] yeni parametre listesini oluşturan karakter dizelerine işaretçilerdir için gelin. Parametre `argv`[`n`+ 1] olmalıdır bir **NULL** parametre listesinin sonunu işaretlemek için işaretçi.

Açık dosyaların bir `_exec` çağrı yapılır yeni işlem içinde açık kalır. İçinde `_execl`, `_execlp`, `_execv`, ve `_execvp` çağrıları, yeni işlem ortam çağırma işleminin devralır. `_execle`, `_execlpe`, `_execve`, ve `_execvpe` çağrılar ortam ayarlarının listesi geçirerek yeni işlem ortamını alter `envp` parametresi. `envp` (son öğe) hariç her öğesi null ile sonlandırılmış dizeye işaret eden bir karakter işaretçiler dizisi, bir ortam değişkeni tanımlamaktır. Bu tür bir dize genellikle formundadır `NAME` = `value` burada `NAME` bir ortam değişkeni adıdır ve `value` bu değişkeni ayarlamak dize değeridir. (Unutmayın `value` çift tırnak işaretleri arasına değil.) Son öğenin `envp` dizisi olmalıdır **NULL**. Zaman `envp` kendisi **NULL**, yeni işlem çağırma işleminin ortam ayarlarını devralır.

Biri ile çalıştırılan bir program `_exec` işlevleri her zaman belleğe yüklendiği alacağı en fazla ayırma alanın programın .exe dosyasının üst bilgisindeki 0xFFFFH varsayılan değerine ayarlandı.

`_exec` Çağrıları açık dosyaların çeviri modları korumak değil. Yeni işlem çağırma işlemden devralındı dosyaları kullanmanız gerekir, kullanın [_setmode](../c-runtime-library/reference/setmode.md) yordamı bu dosyaların çeviri modu istenen moda ayarlanacak. Açıkça temizleme gerekir (kullanarak `fflush` veya `_flushall`) veya herhangi bir akışı önce kapatmak `_exec` işlev çağrısı. Sinyal ayarları korunmaz yapılan çağrılar tarafından oluşturulan yeni işlemlerinde `_exec` yordamları. Sinyal ayarları yeni süreç içerisinde varsayılan sıfırlanır.

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

Aşağıdaki program Crt_args.exe yürütmek için çalıştırın:

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

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../c-runtime-library/process-and-environment-control.md)<br/>
[abort](../c-runtime-library/reference/abort.md)<br/>
[atexit](../c-runtime-library/reference/atexit.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)
