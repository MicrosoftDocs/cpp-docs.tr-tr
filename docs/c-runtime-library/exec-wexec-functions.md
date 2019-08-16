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
ms.openlocfilehash: d31192a25cce86dad6f8e1e8b0258a457d0a5436
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500133"
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

|_exec işlevi soneki|Açıklama|
|----------------------------|-----------------|
|`e`|`envp`, ortam ayarlarına işaretçiler dizisi yeni işleme geçirilir.|
|`l`|Komut satırı bağımsız değişkenleri `_exec` işleve tek tek geçirilir. Genellikle yeni işlem için parametre sayısı önceden bilindiğinde kullanılır.|
|`p`|`PATH`yürütülecek dosyayı bulmak için ortam değişkeni kullanılır.|
|`v`|`argv`, komut satırı bağımsız değişkenlerine işaretçiler dizisi öğesine `_exec`geçirilir. Genellikle yeni işlem için parametre sayısı değişken olduğunda kullanılır.|

## <a name="remarks"></a>Açıklamalar

Her `_exec` işlev yeni bir işlem yükler ve yürütür. Tüm `_exec` işlevler aynı işletim sistemi işlevini ([CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw)) kullanır. `_exec` İşlevler çok baytlı karakter dizesi bağımsız değişkenlerini uygun şekilde otomatik olarak işler ve çok baytlı karakter dizilerini kullanımda olan çok baytlı kod sayfasına göre kullanır. İşlevleri, `_exec` işlevlerinin geniş karakterli sürümleridir. `_wexec` İşlevler `_wexec` çok baytlı karakter dizelerini işleyememesi dışında, kendi aile karşılıklarıyla `_exec` aynı şekilde davranır.

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

`cmdname` Parametresi, yeni işlem olarak yürütülecek dosyayı belirtir. Tam yolu (kökten), kısmi yolu (geçerli çalışma dizininden) veya bir dosya adını belirtebilir. Dosya adı uzantısına sahip değilse veya nokta (.) ile bitmezse `_exec` , işlev adlandırılmış dosyayı arar. `cmdname` Arama başarısız olursa,. com dosya adı uzantısıyla aynı temel adı ve ardından. exe,. bat ve. cmd dosya adı uzantılarını dener. Bir dosya adı uzantısına sahipse,aramadayalnızcaouzantıkullanılır.`cmdname` Bir noktayla `_exec` biterdiğinde, işlev dosya adı uzantısı olmadan arama yapar `cmdname`. `cmdname` `_execlp``PATH` `_execlpe` `cmdname` ,, ve`_execvpe` ortam değişkeni tarafından belirtilen dizinlerde (aynı yordamları kullanarak) arama yapın. `_execvp` Bir sürücü belirticisi veya eğik çizgi `_exec` içeriyorsa(yani,görelibiryolise),çağrıyalnızcabelirtilendosyaiçinaramayapar;yolaranmaz.`cmdname`

`_exec` Çağrı içinde parametre olarak karakter dizelerine bir veya daha fazla işaretçi vererek parametreler yeni işleme geçirilir. Bu karakter dizeleri yeni işlem için parametre listesini oluşturur. Devralınan ortam ayarlarının birleştirilmiş uzunluğu ve yeni işlem için parametre listesini oluşturan dizeler 32 kilobayttan büyük olmamalıdır. Her bir dizenin Sonlandırıcı null karakteri (' \ 0 ') sayıma dahil değildir, ancak boşluk karakterleri (parametreleri ayırmak için otomatik olarak eklenir) sayılır.

> [!NOTE]
>  Dizelerde eklenen boşluklar beklenmeyen davranışlara neden olabilir; Örneğin, dizenin `"hi there"` geçirilmesi `_exec` yeni `"hi"` işlemin iki bağımsız değişken `"there"`elde edilmesine neden olur. Amaç yeni işlemin "Merhaba." adlı bir dosyayı açma süreciydi, işlem başarısız olur. Bunu, dizeyi tırnak içine alarak önleyebilirsiniz: `"\"hi there\""`.

> [!IMPORTANT]
>  Kullanıcı girişini, içeriği açıkça denetlenmeden öğesine `_exec` geçirmeyin. `_exec`, bir [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw) çağrısının oluşmasına neden olacak şekilde, nitelenmemiş yol adlarının olası güvenlik açıklarına yol açabileceğini aklınızda bulundurun.

`_exec` İşlevleri parametrelerini doğrular. Beklenen parametreler null işaretçilerdir, boş dizelerdir veya atlanırsa, `_exec` işlevler [parametre doğrulamasında](../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler olarak `errno` `EINVAL` ayarlanır ve-1 döndürür. Yeni bir işlem yürütülmedi.

Bağımsız `_execl`değişken işaretçileri ayrı parametreler olarak ( `_execve` `_execv` `_execlpe` `_execlp` `_execle`,,, ve içinde `_execvpe` `_execvp`) veya işaretçiler dizisi olarak geçirilebilir (,,, ve). En az bir parametresi, `arg0`yeni işleme geçirilmesi gerekiyor; bu `argv`parametre yeni işlemin [0]. Genellikle, bu parametre bir kopyasıdır `cmdname`. (Farklı bir değer bir hata oluşturmaz.)

,,, Ve`_execlpe` çağrıları genellikle parametre sayısı önceden bilindiğinde kullanılır. `_execle` `_execl` `_execlp` Parametresi `arg0` genellikle bir `cmdname`işaretçisidir. `arg1` İçindeki`argn` parametreler, yeni parametre listesini oluşturan karakter dizelerine işaret. Parametre listesinin sonunu işaretlemek `argn` için bir null işaretçisi gelmelidir.

,,, Ve`_execvpe` çağrıları yeni işlem için parametre sayısı değişken olduğunda faydalıdır. `_execve` `_execv` `_execvp` Parametrelere yönelik işaretçiler dizi `argv`olarak geçirilir. [0 `argv`] parametresi, genellikle bir `cmdname`işaretçisidir. [1 `argv`]- `argv`[`n`] parametreleri, yeni parametre listesini oluşturan karakter dizelerini işaret ettikten sonra. Parametre listesinin `argv`sonunu`n`işaretlemek için [+ 1] parametresi **null** bir işaretçi olmalıdır.

Bir `_exec` çağrı yapıldığında açık olan dosyalar yeni işlemde açık kalır. ,,, Ve`_execvp` çağrılarında, yeni işlem çağıran işlemin ortamını devralır. `_execlp` `_execl` `_execv` `_execle`,, ve `_execlpe` `envp` çağrıları, bir ortam ayarları listesini parametresi aracılığıyla geçirerek yeni işlem için ortamı değiştirir. `_execvpe` `_execve` `envp`, bir karakter işaretçileri dizisi olan her öğe (Final öğesi hariç), bir ortam değişkenini tanımlayan null ile sonlandırılmış bir dizeye işaret eder. Bu tür bir dize genellikle bir ortam `NAME` değişkeninin `NAME` adı olduğu ve `value` söz konusu değişkenin ayarlandığı dize değerinin bulunduğu biçimdedir =. `value` (Çift tırnak `value` işareti içine alınmadığını unutmayın.) `envp` Dizinin son öğesi **null**olmalıdır. Kendisi null olduğunda, yeni işlem çağıran işlemin ortam ayarlarını devralır. `envp`

`_exec` İşlevlerden biriyle yürütülen bir program, programın. exe dosya üstbilgisindeki en büyük ayırma alanının varsayılan olarak 0xFFFFH değerine ayarlanmış olması halinde belleğe yüklenir.

`_exec` Çağrılar, açık dosyaların çeviri modlarını korumaz. Yeni işlemin çağıran işlemden devralınan dosyaları kullanması gerekiyorsa, bu dosyaların çeviri modunu istenen moda ayarlamak için [_setmode](../c-runtime-library/reference/setmode.md) yordamını kullanın. İşlev çağrısından önce herhangi bir akışı `fflush` açık `_flushall`bir şekilde boşaltıp (veya kullanarak) veya kapatmanız gerekir. `_exec` Sinyal ayarları, `_exec` yordamlara çağrılar tarafından oluşturulan yeni işlemlerde korunmaz. Yeni işlemdeki sinyal Ayarları varsayılana sıfırlanır.

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

Crt_args. exe ' yi yürütmek için aşağıdaki programı çalıştırın:

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

**Üstbilgi:** Process. h

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../c-runtime-library/process-and-environment-control.md)<br/>
[abort](../c-runtime-library/reference/abort.md)<br/>
[atexit](../c-runtime-library/reference/atexit.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)
