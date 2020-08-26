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
ms.openlocfilehash: ecfcf88b09a4383fc050e9737a0ffe7203f9a050
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839731"
---
# <a name="_exec-_wexec-functions"></a>_exec, _wexec İşlevleri

Bu ailedeki her bir işlev yeni bir işlem yükler ve yürütür:

:::row:::
   :::column span="":::
      [_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)\
      [_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)\
      [_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)
   :::column-end:::
   :::column span="":::
      [_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)\
      [_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)\
      [_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)
   :::column-end:::
   :::column span="":::
      [_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)\
      [_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)
   :::column-end:::
:::row-end:::

İşlev adının sonundaki harf, çeşitlemesi belirler.

|_exec işlev soneki|Açıklama|
|----------------------------|-----------------|
|`e`|`envp`, ortam ayarlarına işaretçiler dizisi yeni işleme geçirilir.|
|`l`|Komut satırı bağımsız değişkenleri işleve tek tek geçirilir `_exec` . Genellikle yeni işlem için parametre sayısı önceden bilindiğinde kullanılır.|
|`p`|`PATH` yürütülecek dosyayı bulmak için ortam değişkeni kullanılır.|
|`v`|`argv`, komut satırı bağımsız değişkenlerine işaretçiler dizisi öğesine geçirilir `_exec` . Genellikle yeni işlem için parametre sayısı değişken olduğunda kullanılır.|

## <a name="remarks"></a>Açıklamalar

Her `_exec` işlev yeni bir işlem yükler ve yürütür. Tüm `_exec` işlevler aynı işletim sistemi işlevini ([CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw)) kullanır. `_exec`İşlevler çok baytlı karakter dizesi bağımsız değişkenlerini uygun şekilde otomatik olarak işler ve çok baytlı karakter dizilerini kullanımda olan çok baytlı kod sayfasına göre kullanır. `_wexec`İşlevleri, işlevlerinin geniş karakterli sürümleridir `_exec` . `_wexec`İşlevler `_exec` çok baytlı karakter dizelerini işleyememesi dışında, kendi aile karşılıklarıyla aynı şekilde davranır.

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

`cmdname`Parametresi, yeni işlem olarak yürütülecek dosyayı belirtir. Tam yolu (kökten), kısmi yolu (geçerli çalışma dizininden) veya bir dosya adını belirtebilir. `cmdname`Dosya adı uzantısına sahip değilse veya nokta (.) ile bitmezse, `_exec` işlev adlandırılmış dosyayı arar. Arama başarısız olursa,. com dosya adı uzantısıyla aynı temel adı ve ardından. exe,. bat ve. cmd dosya adı uzantılarını dener. `cmdname`Bir dosya adı uzantısına sahipse, aramada yalnızca o uzantı kullanılır. `cmdname`Bir noktayla biterdiğinde, `_exec` işlev `cmdname` dosya adı uzantısı olmadan arama yapar. `_execlp`, `_execlpe` , `_execvp` ve `_execvpe` `cmdname` ortam değişkeni tarafından belirtilen dizinlerde (aynı yordamları kullanarak) arama yapın `PATH` . `cmdname`Bir sürücü belirticisi veya eğik çizgi içeriyorsa (yani, göreli bir yol ise), `_exec` çağrı yalnızca belirtilen dosya için arama yapar; yol aranmaz.

Çağrı içinde parametre olarak karakter dizelerine bir veya daha fazla işaretçi vererek parametreler yeni işleme geçirilir `_exec` . Bu karakter dizeleri yeni işlem için parametre listesini oluşturur. Devralınan ortam ayarlarının birleştirilmiş uzunluğu ve yeni işlem için parametre listesini oluşturan dizeler 32 kilobayttan büyük olmamalıdır. Her bir dizenin Sonlandırıcı null karakteri (' \ 0 ') sayıma dahil değildir, ancak boşluk karakterleri (parametreleri ayırmak için otomatik olarak eklenir) sayılır.

> [!NOTE]
> Dizelerde eklenen boşluklar beklenmeyen davranışlara neden olabilir; Örneğin, dizenin geçirilmesi `_exec` `"hi there"` yeni işlemin iki bağımsız değişken elde edilmesine neden olur `"hi"` `"there"` . Amaç yeni işlemin "Merhaba." adlı bir dosyayı açma süreciydi, işlem başarısız olur. Bunu, dizeyi tırnak içine alarak önleyebilirsiniz: `"\"hi there\""` .

> [!IMPORTANT]
> Kullanıcı girişini `_exec` , içeriği açıkça denetlenmeden öğesine geçirmeyin. `_exec` , bir [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw) çağrısının oluşmasına neden olacak şekilde, nitelenmemiş yol adlarının olası güvenlik açıklarına yol açabileceğini aklınızda bulundurun.

`_exec`İşlevleri parametrelerini doğrular. Beklenen parametreler null işaretçilerdir, boş dizelerdir veya atlanırsa, `_exec` Işlevler [parametre doğrulamasında](../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler olarak ayarlanır `errno` `EINVAL` ve-1 döndürür. Yeni bir işlem yürütülmedi.

Bağımsız değişken işaretçileri ayrı parametreler olarak (,,, `_execl` ve içinde `_execle` `_execlp` `_execlpe` ) veya işaretçiler dizisi olarak geçirilebilir (,,, `_execv` `_execve` `_execvp` ve `_execvpe` ). En az bir parametresi, `arg0` yeni işleme geçirilmesi gerekiyor; bu parametre `argv` yeni işlemin [0]. Genellikle, bu parametre bir kopyasıdır `cmdname` . (Farklı bir değer bir hata oluşturmaz.)

`_execl`,, `_execle` , `_execlp` Ve `_execlpe` çağrıları genellikle parametre sayısı önceden bilindiğinde kullanılır. Parametresi `arg0` genellikle bir işaretçisidir `cmdname` . İçindeki parametreler `arg1` , `argn` yeni parametre listesini oluşturan karakter dizelerine işaret. `argn`Parametre listesinin sonunu işaretlemek için bir null işaretçisi gelmelidir.

`_execv`,, `_execve` , `_execvp` Ve `_execvpe` çağrıları yeni işlem için parametre sayısı değişken olduğunda faydalıdır. Parametrelere yönelik işaretçiler dizi olarak geçirilir `argv` . `argv`[0] parametresi, genellikle bir işaretçisidir `cmdname` . [ `argv` 1]- `argv` [] parametreleri, `n` yeni parametre listesini oluşturan karakter dizelerini işaret ettikten sonra. Parametre `argv` `n` listesinin sonunu işaretlemek için [+ 1] parametresi **null** bir işaretçi olmalıdır.

Bir çağrı yapıldığında açık olan dosyalar `_exec` Yeni işlemde açık kalır. `_execl`,, `_execlp` , `_execv` Ve `_execvp` çağrılarında, yeni işlem çağıran işlemin ortamını devralır. `_execle`, `_execlpe` , `_execve` ve `_execvpe` çağrıları, bir ortam ayarları listesini parametresi aracılığıyla geçirerek yeni işlem için ortamı değiştirir `envp` . `envp` , bir karakter işaretçileri dizisi olan her öğe (Final öğesi hariç), bir ortam değişkenini tanımlayan null ile sonlandırılmış bir dizeye işaret eder. Bu tür bir dize genellikle `NAME` = `value` `NAME` bir ortam değişkeninin adı olduğu ve `value` söz konusu değişkenin ayarlandığı dize değerinin bulunduğu biçimdedir. ( `value` Çift tırnak işareti içine alınmadığını unutmayın.) Dizinin son öğesi `envp` **null**olmalıdır. `envp`Kendisi **null**olduğunda, yeni işlem çağıran işlemin ortam ayarlarını devralır.

İşlevlerden biriyle yürütülen bir program `_exec` , programın. exe dosya üstbilgisindeki en büyük ayırma alanının varsayılan olarak 0xFFFFH değerine ayarlanmış olması halinde belleğe yüklenir.

`_exec`Çağrılar, açık dosyaların çeviri modlarını korumaz. Yeni işlemin çağıran işlemden devralınan dosyaları kullanması gerekiyorsa, bu dosyaların çeviri modunu istenen moda ayarlamak için [_setmode](../c-runtime-library/reference/setmode.md) yordamını kullanın. `fflush` `_flushall` İşlev çağrısından önce herhangi bir akışı açık bir şekilde boşaltıp (veya kullanarak) veya kapatmanız gerekir `_exec` . Sinyal ayarları, yordamlara çağrılar tarafından oluşturulan yeni işlemlerde korunmaz `_exec` . Yeni işlemdeki sinyal Ayarları varsayılana sıfırlanır.

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

Crt_args.exe yürütmek için aşağıdaki programı çalıştırın:

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

[İşlem ve ortam denetimi](../c-runtime-library/process-and-environment-control.md)<br/>
[durdur](../c-runtime-library/reference/abort.md)<br/>
[atexit](../c-runtime-library/reference/atexit.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)<br/>
[_spawn, _wspawn Işlevleri](../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)
