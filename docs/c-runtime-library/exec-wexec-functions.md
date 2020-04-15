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
ms.openlocfilehash: 52c9727db544d8b124b37cc5beae369ae06abe10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351657"
---
# <a name="_exec-_wexec-functions"></a>_exec, _wexec İşlevleri

Bu ailedeki her işlev yeni bir işlem yükler ve yürütür:

|||
|-|-|
|[_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)|[_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)|
|[_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)|[_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)|
|[_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|[_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|
|[_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|[_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|

Işlev adının sonundaki harf varyasyonu belirler.

|_exec fonksiyonu soneki|Açıklama|
|----------------------------|-----------------|
|`e`|`envp`, ortam ayarlarına işaretçiler dizisi, yeni işleme geçirilir.|
|`l`|Komut satırı bağımsız değişkenleri `_exec` tek tek işlemeye geçirilir. Genellikle yeni işlem için parametre sayısı önceden bilindiğinde kullanılır.|
|`p`|`PATH`çevre değişkeni yürütmek için dosyayı bulmak için kullanılır.|
|`v`|`argv`, komut satırı bağımsız değişkenlerine işaretçiler `_exec`dizisi, . Genellikle yeni işlem için parametre sayısı değişken olduğunda kullanılır.|

## <a name="remarks"></a>Açıklamalar

Her `_exec` işlev yeni bir işlem yükler ve yürütür. Tüm `_exec` işlevler aynı işletim sistemi işlevini kullanır ([CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw)). İşlevler, `_exec` çok bayt karakterli dize bağımsız değişkenlerini uygun şekilde işleyerek, şu anda kullanılmakta olan çok bayt kod sayfasına göre çok bayt karakter dizilerini tanıyarak çalışır. İşlevler `_wexec` işlevlerin `_exec` geniş karakterli sürümleridir. Çok `_wexec` bayt karakterli `_exec` dizeleri işlemedikleri sürece işlevler aile karşılıklarıyla aynı şekilde çalışır.

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

Parametre, `cmdname` yürütülecek dosyayı yeni işlem olarak belirtir. Tam bir yol (kökten), kısmi bir yol (geçerli çalışma dizininden) veya dosya adı belirtebilir. Dosya `cmdname` adı uzantısı yoksa veya bir dönemle (.) `_exec` bitmiyorsa, işlev adlandırılmış dosyayı arar. Arama başarısız olursa, .com dosya adı uzantısı ve sonra .exe, .bat ve .cmd dosya adı uzantıları ile aynı temel adı çalışır. Dosya `cmdname` adı uzantısı varsa, aramada yalnızca bu uzantı kullanılır. Bir `cmdname` dönemle biterse, `_exec` işlev `cmdname` dosya adı uzantısı olmadan arama lar yaparsa. `_execlp`, `_execlpe` `_execvp`, `_execvpe` , `cmdname` ve `PATH` arama (aynı yordamları kullanarak) çevre değişkeni tarafından belirtilen dizinlerde. Sürücü `cmdname` belirtici veya herhangi bir kesik içeriyorsa (yani göreceli bir `_exec` yolsa), arama yalnızca belirtilen dosyayı arar; yol aranmaz.

`_exec` Parametreler, çağrıdaki parametreler olarak karakter dizelerine bir veya daha fazla işaretçi vererek yeni işleme aktarılır. Bu karakter dizeleri yeni işlem için parametre listesini oluşturur. Devralınan ortam ayarlarının ve yeni işlem için parametre listesini oluşturan dizelerin toplam uzunluğu 32 kilobayt'ı geçmemelidir. Her dize için sonlandırıcı null karakter ('\0') sayıma dahil edilmez, ancak boşluk karakterleri (parametreleri ayırmak için otomatik olarak eklenir) sayılır.

> [!NOTE]
> Dizeleri katıştırılmış boşluklar beklenmeyen davranışlara neden olabilir; `_exec` örneğin, dize `"hi there"` geçen yeni işlem iki bağımsız `"hi"` değişken `"there"`almak neden olur ve . Amaç, yeni işlemin "merhaba there" adlı bir dosyayı açmasıiçin olsaydı, işlem başarısız olur. Dize alıntı yaparak bu önleyebilirsiniz: `"\"hi there\""`.

> [!IMPORTANT]
> İçeriğini açıkça `_exec` denetlemeden kullanıcı girişini geçirmeyin. `_exec`createprocess için bir [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw) çağrı yla sonuçlanır, böylece niteliksiz yol adlarının olası güvenlik açıklarına yol açabileceğini unutmayın.

Fonksiyonlar `_exec` parametrelerini doğrular. Beklenen parametreler null işaretçileri, boş dizeleri veya `_exec` atlanan ise, işlevler [Parametre Doğrulama'da](../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, `errno` `EINVAL` bu işlevler -1 olarak ayarlanır ve döndürün. Yeni bir işlem yürütülmez.

Bağımsız değişken işaretçileri ayrı parametreler `_execl`olarak `_execle` `_execlp`(içinde `_execlpe`, , ve ) veya `_execv` `_execve`işaretçiler dizisi olarak (içinde , , `_execvp`ve `_execvpe`) geçirilebilir. En az bir `arg0`parametre, yeni işleme geçirilmelidir; bu parametre `argv`yeni işlemin [0] olduğunu. Genellikle, bu parametre `cmdname`bir kopyasıdır. (Farklı bir değer hata üretmez.)

`_execl`Parametre `_execle` `_execlp`sayısı `_execlpe` önceden bilindiğinde, aramalar ve çağrılar genellikle kullanılır. Parametre `arg0` genellikle `cmdname`bir işaretçi . `arg1` Parametreler, `argn` yeni parametre listesini oluşturan karakter dizelerine işaret eder. Parametre listesinin `argn` sonunu işaretlemek için null işaretçisinin izlemesi gerekir.

Yeni `_execv` `_execve`işlemin `_execvp`parametreleri değişken olduğunda , , ve `_execvpe` aramalar yararlıdır. Parametrelere işaretçiler bir dizi olarak `argv`geçirilir. Parametre `argv`[0] genellikle `cmdname`bir işaretçi. [1] ile `argv` `argv`[`n`] parametreleri, yeni parametre listesini oluşturan karakter dizelerini işaret eder. [ `argv``n`+1] parametresi, parametre listesinin sonunu işaretlemek için **null** işaretçisi olmalıdır.

`_exec` Arama yapıldığında açık olan dosyalar yeni işlemde açık kalır. `_execl`Yeni `_execlp`işlem, `_execvp` çağrı `_execv`işleminin ortamını devralır. `_execle`, `_execlpe` `_execve`, `_execvpe` , ve aramalar `envp` parametre üzerinden ortam ayarlarının bir listesini geçirerek yeni işlem için ortamı değiştirir. `envp`her öğe (son öğe hariç) bir ortam değişkenini tanımlayan null-sonlandırılan dize işaretleyen karakter işaretçileri dizisidir. Böyle bir dize `NAME` = `value` genellikle `NAME` bir ortam değişkeninin `value` adı olan forma sahiptir ve bu değişkenin ayarlandığı dize değeridir. (Çift `value` tırnak işaretlerine dahil olmayana dikkat edin.) `envp` Dizinin son öğesi **NULL**olmalıdır. Kendisi `envp` **NULL**olduğunda, yeni işlem arama işleminin ortam ayarlarını devralır.

`_exec` İşlevlerden biriyle yürütülen bir program, programın .exe dosya üstbilgisindeki maksimum ayırma alanı 0xFFFFH varsayılan değerine ayarlanmış gibi her zaman belleğe yüklenir.

Aramalar, `_exec` açık dosyaların çeviri modlarını korumaz. Yeni işlem arama işleminden devralınan dosyaları kullanıyorsa, bu dosyaların çeviri modunu istenen moda ayarlamak için [_setmode](../c-runtime-library/reference/setmode.md) yordamını kullanın. İşlev çağrısından önce `fflush` `_flushall`herhangi bir akışı açıkça `_exec` temizlemeniz (kullanmanız veya) kapatmanız gerekir. İşaret `_exec` ayarları, yordamlara yapılan çağrılar tarafından oluşturulan yeni işlemlerde korunmaz. Sinyal ayarları yeni işlemde varsayılan olarak sıfırlanır.

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

**Üstbilgi:** process.h

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../c-runtime-library/process-and-environment-control.md)<br/>
[Iptal](../c-runtime-library/reference/abort.md)<br/>
[atexit](../c-runtime-library/reference/atexit.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)
