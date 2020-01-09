---
title: _spawn, _wspawn İşlevleri
ms.date: 11/04/2016
api_location:
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 81f4bf6c60a0c0e4011536e8d3bc104bbc33e04f
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301710"
---
# <a name="_spawn-_wspawn-functions"></a>_spawn, _wspawn İşlevleri

`_spawn` işlevlerin her biri yeni bir işlem oluşturur ve yürütür:

|||
|-|-|
|[_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|[_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|
|[_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|[_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|
|[_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|[_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|
|[_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|[_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|

İşlev adının sonundaki harfler çeşitlemesi tespit edin.

|Harfi|Değişken|
|-|-|
| `e`  | `envp`, ortam ayarlarına işaretçiler dizisi yeni işleme geçirilir.  |
| `l`  | Komut satırı bağımsız değişkenleri tek tek `_spawn` işleve geçirilir. Bu sonek genellikle yeni bir işleme yönelik bir dizi parametre önceden bilindiğinde kullanılır.  |
| `p`  | `PATH` ortam değişkeni, yürütülecek dosyayı bulmak için kullanılır.  |
| `v`  | `argv`, komut satırı bağımsız değişkenlerine işaretçiler dizisi `_spawn` işleve geçirilir. Bu sonek genellikle yeni bir işleme yönelik bir dizi parametrenin değişken olduğu durumlarda kullanılır.  |

## <a name="remarks"></a>Açıklamalar

`_spawn` işlevlerin her biri yeni bir işlem oluşturur ve yürütür. Çok baytlı karakter dizisi bağımsız değişkenlerini uygun şekilde otomatik olarak işler ve çok baytlı karakter dizilerini kullanımda olan çok baytlı kod sayfasına göre tanıyor. `_wspawn` işlevleri, `_spawn` işlevlerinin geniş karakterli sürümleridir; çok baytlı karakter dizelerini işlemez. Aksi takdirde, `_wspawn` işlevleri `_spawn` karşılıklarıyla aynı şekilde davranır.

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

Yeni işlemi yüklemek ve yürütmek için yeterli bellek kullanılabilir olmalıdır. `mode` bağımsız değişkeni, `_spawn`önce ve sırasında çağıran işlem tarafından gerçekleştirilen eylemi belirler. `mode` için aşağıdaki değerler, Process. h içinde tanımlanmıştır:

|||
|-|-|
| `_P_OVERLAY`  | Çağıran işlemi yok etme, çağırma işlemini yok etme (`_exec` çağrılarıyla aynı etkiyi).  |
| `_P_WAIT`  | Yeni işlemin yürütülmesi tamamlanana kadar çağıran bir iş parçacığını askıya alır (zaman uyumlu `_spawn`).  |
| `_P_NOWAIT` veya `_P_NOWAITO`  | Yeni işlemle aynı anda bir arama işlemini yürütmeye devam eder (zaman uyumsuz `_spawn`).  |
| `_P_DETACH`  | Çağıran işlemi yürütmeye devam eder; Yeni işlem, konsola veya klavyeye erişim olmadan arka planda çalıştırılır. Yeni işleme karşı `_cwait` çağrılar başarısız olur (zaman uyumsuz `_spawn`).  |

`cmdname` bağımsız değişkeni, yeni işlem olarak yürütülen dosyayı belirtir ve tam yolu (kökten), kısmi yolu (geçerli çalışma dizininden) veya yalnızca bir dosya adını belirtebilir. `cmdname` dosya adı uzantısına sahip değilse veya nokta (.) ile bitmezse, `_spawn` işlevi önce. com dosya adı uzantısını, sonra. exe dosya adı uzantısını,. bat dosya adı uzantısını ve son olarak. cmd dosya adı uzantısını dener.

`cmdname` bir dosya adı uzantısına sahipse, yalnızca o uzantı kullanılır. `cmdname` bir noktayla sona ererse `_spawn` çağrı, dosya adı uzantısı olmayan `cmdname` arar. `_spawnlp`, `_spawnlpe`, `_spawnvp`ve `_spawnvpe` işlevleri, `cmdname` ortam değişkeni tarafından belirtilen dizinlerde `PATH` (aynı yordamları kullanarak) arar.

`cmdname` bir sürücü belirticisi veya eğik çizgi içeriyorsa (yani, göreli bir yollarsa), `_spawn` çağrı yalnızca belirtilen dosya için arama yapar; yol arama yapılmaz.

Geçmişte, bu işlevlerden bazıları başarılı ' de sıfıra `errno`; geçerli davranış, C standardı tarafından belirtilen şekilde `errno` dokunulmadan çıkmıyor. Eski davranışa benzemeniz gerekiyorsa, bu işlevleri çağırmadan hemen önce `errno` sıfır olarak ayarlayın.

> [!NOTE]
>  Doğru kaplama başlatma ve sonlandırmayı sağlamak için `setjmp` veya `longjmp` işlevini, bir kaplama yordamı girmek veya bırakmak için kullanmayın.

## <a name="arguments-for-the-spawned-process"></a>Oluşturulan Işlem için bağımsız değişkenler

Bağımsız değişkenleri yeni işleme geçirmek için, `_spawn` çağrısında bağımsız değişken olarak karakter dizelerine bir veya daha fazla işaretçi verin. Bu karakter dizeleri oluşturulan işlemin bağımsız değişken listesini oluşturur. Yeni işlem için bağımsız değişken listesini oluşturan dizelerin Birleşik uzunluğu 1024 baytı aşmamalıdır. Her bir dizenin Sonlandırıcı null karakteri (' \ 0 ') sayıma dahil değildir, ancak boşluk karakterleri (ayrı bağımsız değişkenlere otomatik olarak eklenir) dahil edilir.

> [!NOTE]
>  Dizelerde eklenen boşluklar beklenmeyen davranışlara neden olabilir; Örneğin, `"hi there"` dize `_spawn` geçirmek yeni işleme, `"hi"` ve `"there"`iki bağımsız değişken getirmeye neden olur. Amaç yeni işlemin "Merhaba." adlı bir dosyayı açma süreciydi, işlem başarısız olur. Bunu, dizeyi tırnak içine alarak önleyebilirsiniz: `"\"hi there\""`.

> [!IMPORTANT]
>  Kullanıcı girişini, içeriği açıkça denetlenmeden `_spawn` iletmeyin. `_spawn`, [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw) çağrısının oluşmasına neden olacak. bu nedenle, nitelenmemiş yol adlarının olası güvenlik açıklarına neden olabileceğini aklınızda bulundurun.

Bağımsız değişken işaretçilerini ayrı bağımsız değişkenler olarak (`_spawnl`, `_spawnle`, `_spawnlp`ve `_spawnlpe`) veya bir işaretçi dizisi olarak (`_spawnv`, `_spawnve`, `_spawnvp`ve `_spawnvpe`) geçirebilirsiniz. Oluşturulan işleme en az bir bağımsız değişken, `arg0` veya `argv`[0] geçirmeniz gerekir. Kurala göre, bu bağımsız değişken programın komut satırına yazdığınız addır. Farklı bir değer hata oluşturmaz.

`_spawnl`, `_spawnle`, `_spawnlp`ve `_spawnlpe` çağrıları genellikle bağımsız değişken sayısının önceden bilinen olduğu durumlarda kullanılır. `arg0` bağımsız değişkeni genellikle `cmdname`işaretçisidir. `arg1` ile `argn` arasındaki bağımsız değişkenler, yeni bağımsız değişken listesini oluşturan karakter dizelerinin işaretçileridir. `argn`, bağımsız değişken listesinin sonunu işaretlemek için **null** bir işaretçi olmalıdır.

`_spawnv`, `_spawnve`, `_spawnvp`ve `_spawnvpe` çağrıları, yeni işlemde değişken sayıda bağımsız değişken olduğunda yararlıdır. Bağımsız değişkenlerin işaretçileri bir dizi olarak geçirilir, `argv` *.* `argv`[0] bağımsız değişkeni, genellikle gerçek moddaki yolun veya korunan moddaki program adının bir işaretçisidir ve `argv`[`n`] aracılığıyla `argv`[1], yeni bağımsız değişken listesini oluşturan karakter dizelerinin işaretçileridir. Bağımsız değişken listesinin sonunu işaretlemek için `argv`[`n` + 1] bağımsız değişkeni **null** bir işaretçi olmalıdır.

## <a name="environment-of-the-spawned-process"></a>Oluşturulan Işlemin ortamı

Bir `_spawn` çağrısı yapıldığında açık olan dosyalar yeni işlemde açık kalır. `_spawnl`, `_spawnlp`, `_spawnv`ve `_spawnvp` çağrılarında, yeni işlem çağıran işlemin ortamını devralır. `_spawnle`, `_spawnlpe`, `_spawnve`ve `_spawnvpe` çağrılarını, bir ortam ayarları listesini `envp` bağımsız değişkeniyle geçirerek yeni işlem için bir ortam değiştirmek üzere kullanabilirsiniz. `envp` bağımsız değişkeni, bir ortam değişkenini tanımlayan null ile sonlandırılmış bir dizeye işaret eden, her öğe (Final öğesi hariç) bir karakter işaretçileri dizisidir. Bu tür bir dize genellikle `NAME` bir ortam değişkeninin adı olduğu ve `value` söz konusu değişkenin ayarlandığı dize değeri olan `NAME`=`value`. (`value` çift tırnak işareti içine alınmadığını unutmayın.) `envp` dizisinin son öğesi **null**olmalıdır. `envp` kendisi **null**olduğunda, oluşturulan işlem üst işlemin ortam ayarlarını devralır.

`_spawn` işlevleri, çeviri modu da dahil olmak üzere açık dosyalarla ilgili tüm bilgileri yeni işleme geçirebilir. Bu bilgiler, ortamdaki `C_FILE_INFO` girişi aracılığıyla gerçek modda geçirilir. Başlangıç kodu normalde bu girişi işler ve sonra ortamdan siler. Ancak, bir `_spawn` işlevi C olmayan bir işlem içeriyorsa, bu giriş ortamda kalır. Ortam bilgileri, gerçek modda ikili biçimde geçirildiğinden, ortamın yazdırılması Bu girdinin tanım dizesinde grafik karakterlerini gösterir. Normal işlemler üzerinde başka bir etkiye sahip olmamalıdır. Korumalı modda, ortam bilgileri metin biçiminde geçirilir ve bu nedenle grafik karakteri içermez.

`_spawn` işlevini çağırmadan önce, `fflush` veya `_flushall`kullanarak) veya herhangi bir akışı kapatmanız gerekir.

`_spawn` yordamlarına yapılan çağrılar tarafından oluşturulan yeni süreçler, sinyal ayarlarını korumaz. Bunun yerine, oluşturulan işlem sinyal ayarlarını varsayılana sıfırlar.

## <a name="redirecting-output"></a>Çıktıyı yeniden yönlendirme

Bir DLL veya GUI uygulamasından `_spawn` arıyorsanız ve çıktıyı bir kanala yönlendirmek istiyorsanız iki seçeneğiniz vardır:

- Win32 API kullanarak bir kanal oluşturun, ardından [AllocConsole](/windows/console/allocconsole)'u çağırın, başlangıç yapısındaki tanıtıcı değerlerini ayarlayın ve [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw)çağırın.

- [_Popen çağırın, bu,](../c-runtime-library/reference/popen-wpopen.md) bir kanal oluşturur ve **cmd. exe/c** (veya **Command. exe/c**) kullanarak uygulamayı çağırır _wpopen.

## <a name="example"></a>Örnek

```c
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

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../c-runtime-library/process-and-environment-control.md)<br/>
[abort](../c-runtime-library/reference/abort.md)<br/>
[atexit](../c-runtime-library/reference/atexit.md)<br/>
[_exec, _wexec İşlevleri](../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_flushall](../c-runtime-library/reference/flushall.md)<br/>
[_getmbcp](../c-runtime-library/reference/getmbcp.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)<br/>
[_setmbcp](../c-runtime-library/reference/setmbcp.md)<br/>
[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)
