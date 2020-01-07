---
title: _exec, _wexec İşlevleri
ms.date: 11/04/2016
api_location:
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: dab670c5baef1c51c39a4c936380fab92c5103cc
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300318"
---
# <a name="_exec-_wexec-functions"></a>_exec, _wexec İşlevleri

Bu ailedeki her bir işlev yeni bir işlem yükler ve yürütür:

|||
|-|-|
|[_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)|[_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)|
|[_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)|[_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)|
|[_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|[_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|
|[_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|[_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|

İşlev adının sonundaki harf, çeşitlemesi belirler.

|_exec işlev soneki|Açıklama|
|----------------------------|-----------------|
|`e`|`envp`, ortam ayarlarına işaretçiler dizisi yeni işleme geçirilir.|
|`l`|Komut satırı bağımsız değişkenleri tek tek `_exec` işleve geçirilir. Genellikle yeni işlem için parametre sayısı önceden bilindiğinde kullanılır.|
|`p`|`PATH` ortam değişkeni, yürütülecek dosyayı bulmak için kullanılır.|
|`v`|`argv`, komut satırı bağımsız değişkenlerine işaretçiler dizisi `_exec`geçirilir. Genellikle yeni işlem için parametre sayısı değişken olduğunda kullanılır.|

## <a name="remarks"></a>Açıklamalar

Her `_exec` işlevi yeni bir işlem yükler ve yürütür. Tüm `_exec` işlevleri aynı işletim sistemi işlevini ([CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw)) kullanır. `_exec` işlevleri, çok baytlı karakterli dize bağımsız değişkenlerini uygun şekilde otomatik olarak işler ve çok baytlı karakter dizilerini kullanımda olan çok baytlı kod sayfasına göre tanıyor. `_wexec` işlevleri, `_exec` işlevlerinin geniş karakterli sürümleridir. `_wexec` işlevleri, çok baytlı karakter dizelerini işleyememesi dışında `_exec` aile karşılıklarıyla aynı şekilde davranır.

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

`cmdname` parametresi, yeni işlem olarak yürütülecek dosyayı belirtir. Tam yolu (kökten), kısmi yolu (geçerli çalışma dizininden) veya bir dosya adını belirtebilir. `cmdname` dosya adı uzantısına sahip değilse veya nokta (.) ile bitmezse, `_exec` işlevi adlandırılmış dosyayı arar. Arama başarısız olursa,. com dosya adı uzantısıyla aynı temel adı ve ardından. exe,. bat ve. cmd dosya adı uzantılarını dener. `cmdname` bir dosya adı uzantısına sahipse, aramada yalnızca o uzantı kullanılır. `cmdname` bir noktayla biterdiğinde, `_exec` işlevi dosya adı uzantısı olmayan `cmdname` arar. `cmdname` ortam değişkeni tarafından belirtilen dizinlerde `PATH` (aynı yordamları kullanarak) `_execlp`, `_execlpe`, `_execvp`ve `_execvpe` arama. `cmdname` bir sürücü belirticisi veya eğik çizgi içeriyorsa (yani, göreli bir yollarsa), `_exec` çağrı yalnızca belirtilen dosya için arama yapar; yol aranmadı.

Parametreler, `_exec` çağrısında parametre olarak karakter dizelerine bir veya daha fazla işaretçi vererek yeni işleme geçirilir. Bu karakter dizeleri yeni işlem için parametre listesini oluşturur. Devralınan ortam ayarlarının birleştirilmiş uzunluğu ve yeni işlem için parametre listesini oluşturan dizeler 32 kilobayttan büyük olmamalıdır. Her bir dizenin Sonlandırıcı null karakteri (' \ 0 ') sayıma dahil değildir, ancak boşluk karakterleri (parametreleri ayırmak için otomatik olarak eklenir) sayılır.

> [!NOTE]
>  Dizelerde eklenen boşluklar beklenmeyen davranışlara neden olabilir; Örneğin, `"hi there"` dize `_exec` geçirmek yeni işleme, `"hi"` ve `"there"`iki bağımsız değişken getirmeye neden olur. Amaç yeni işlemin "Merhaba." adlı bir dosyayı açma süreciydi, işlem başarısız olur. Bunu, dizeyi tırnak içine alarak önleyebilirsiniz: `"\"hi there\""`.

> [!IMPORTANT]
>  Kullanıcı girişini, içeriği açıkça denetlenmeden `_exec` iletmeyin. `_exec`, [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw) çağrısının oluşmasına neden olacak. bu nedenle, nitelenmemiş yol adlarının olası güvenlik açıklarına neden olabileceğini aklınızda bulundurun.

`_exec` işlevleri parametrelerini doğrular. Beklenen parametreler null işaretçiler, boş dizeler veya atlanırsa, `_exec` işlevleri [parametre doğrulamasında](../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler `EINVAL` `errno` ve-1 döndürür. Yeni bir işlem yürütülmedi.

Bağımsız değişken işaretçileri ayrı parametreler olarak geçirilebilir (`_execl`, `_execle`, `_execlp`ve `_execlpe`) veya işaretçiler dizisi (`_execv`, `_execve`, `_execvp`ve `_execvpe`). En az bir parametre olan `arg0`yeni işleme geçirilmesi gerekir; Bu parametre, yeni işlemin `argv`[0]. Genellikle, bu parametre `cmdname`kopyasıdır. (Farklı bir değer bir hata oluşturmaz.)

`_execl`, `_execle`, `_execlp`ve `_execlpe` çağrıları genellikle parametre sayısı önceden bilindiğinde kullanılır. `arg0` parametresi, genellikle `cmdname`işaretçisidir. `argn` üzerinden `arg1` parametreler, yeni parametre listesini oluşturan karakter dizelerine işaret. Parametre listesinin sonunu işaretlemek için null işaretçisinin `argn` izlemesi gerekir.

`_execv`, `_execve`, `_execvp`ve `_execvpe` çağrıları, yeni işleme ait parametrelerin sayısı değişken olduğunda faydalıdır. Parametrelere yönelik işaretçiler dizi olarak geçirilir, `argv`. `argv`[0] parametresi, genellikle `cmdname`işaretçisidir. `argv`[`n`] aracılığıyla `argv`[1] parametreleri, yeni parametre listesini oluşturan karakter dizelerine işaret edin. Parametre listesinin sonunu işaretlemek için `argv`[`n`+ 1] parametresi **null** bir işaretçi olmalıdır.

Bir `_exec` çağrısı yapıldığında açık olan dosyalar yeni işlemde açık kalır. `_execl`, `_execlp`, `_execv`ve `_execvp` çağrılarında, yeni süreç çağıran işlemin ortamını devralır. `_execle`, `_execlpe`, `_execve`ve `_execvpe` çağrıları, bir ortam ayarları listesini `envp` parametresi aracılığıyla geçirerek yeni işlem için ortamı değiştirir. `envp`, her öğesi (Final öğesi hariç), bir ortam değişkenini tanımlayan null ile sonlandırılmış bir dizeye işaret eden bir karakter işaretçileri dizisidir. Bu tür bir dize genellikle `NAME` bir ortam değişkeninin adı olduğu ve `value` söz konusu değişkenin ayarlandığı dize değeri olan `NAME`=`value`. (`value` çift tırnak işareti içine alınmadığını unutmayın.) `envp` dizisinin son öğesi **null**olmalıdır. `envp` kendisi **null**olduğunda, yeni işlem çağıran işlemin ortam ayarlarını devralır.

`_exec` işlevlerinden biriyle yürütülen bir program, programın. exe dosya üstbilgisindeki en büyük ayırma alanının varsayılan 0xFFFFH değerine ayarlanmış olması halinde belleğe her zaman yüklenir.

`_exec` çağrısı, açık dosyaların çeviri modlarını korumaz. Yeni işlemin çağıran işlemden devralınan dosyaları kullanması gerekiyorsa, bu dosyaların çeviri modunu istenen moda ayarlamak için [_setmode](../c-runtime-library/reference/setmode.md) yordamını kullanın. `_exec` işlev çağrısından önce, `fflush` veya `_flushall`kullanarak) veya herhangi bir akışı kapatmanız gerekir. Sinyal ayarları, `_exec` yordamlarına çağrılar tarafından oluşturulan yeni işlemlerde korunmaz. Yeni işlemdeki sinyal Ayarları varsayılana sıfırlanır.

## <a name="example"></a>Örnek

```c
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

Crt_args. exe ' yi yürütmek için aşağıdaki programı çalıştırın:

```c
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

**Üstbilgi:** Process. h

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../c-runtime-library/process-and-environment-control.md)<br/>
[abort](../c-runtime-library/reference/abort.md)<br/>
[atexit](../c-runtime-library/reference/atexit.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)
