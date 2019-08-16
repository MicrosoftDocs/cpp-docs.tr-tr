---
title: _spawn, _wspawn İşlevleri
ms.date: 11/04/2016
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
ms.openlocfilehash: 8ab368378775102b708635b551c046a326adfecb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498902"
---
# <a name="_spawn-_wspawn-functions"></a>_spawn, _wspawn İşlevleri

`_spawn` İşlevlerin her biri yeni bir işlem oluşturur ve yürütür:

|||
|-|-|
|[_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|[_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|
|[_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|[_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|
|[_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|[_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|
|[_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|[_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|

İşlev adının sonundaki harfler çeşitlemesi tespit edin.

|Harfi|Varyantı|
|-|-|
| `e`  | `envp`, ortam ayarlarına işaretçiler dizisi yeni işleme geçirilir.  |
| `l`  | Komut satırı bağımsız değişkenleri `_spawn` işleve tek tek geçirilir. Bu sonek genellikle yeni bir işleme yönelik bir dizi parametre önceden bilindiğinde kullanılır.  |
| `p`  | `PATH`yürütülecek dosyayı bulmak için ortam değişkeni kullanılır.  |
| `v`  | `argv`, komut satırı bağımsız değişkenlerine işaretçiler dizisi `_spawn` işlevine geçirilir. Bu sonek genellikle yeni bir işleme yönelik bir dizi parametrenin değişken olduğu durumlarda kullanılır.  |

## <a name="remarks"></a>Açıklamalar

`_spawn` İşlevlerin her biri yeni bir işlem oluşturur ve yürütür. Çok baytlı karakter dizisi bağımsız değişkenlerini uygun şekilde otomatik olarak işler ve çok baytlı karakter dizilerini kullanımda olan çok baytlı kod sayfasına göre tanıyor. `_wspawn` İşlevleri `_spawn` işlevlerinin geniş karakterli sürümleridir; çok baytlı karakter dizelerini işlemez. Aksi takdirde, `_wspawn` işlevler karşılıklarıyla `_spawn` aynı şekilde davranır.

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

Yeni işlemi yüklemek ve yürütmek için yeterli bellek kullanılabilir olmalıdır. Bağımsız değişkeni, çağıran işlem tarafından ve sırasında `_spawn`gerçekleştirilecek eylemi belirler. `mode` İçin `mode` aşağıdaki değerler, Process. h içinde tanımlanmıştır:

|||
|-|-|
| `_P_OVERLAY`  | Çağıran işlemi yok etme, çağırma işlemini yok etme ( `_exec` çağrılarla aynı etkiyi).  |
| `_P_WAIT`  | Yeni işlemin yürütülmesi tamamlanana kadar çağıran bir iş parçacığını askıya alır (zaman uyumlu `_spawn`).  |
| `_P_NOWAIT` veya `_P_NOWAITO`  | Yeni işlemle (zaman uyumsuz `_spawn`) bir arama işlemini eşzamanlı olarak yürütmeye devam eder.  |
| `_P_DETACH`  | Çağıran işlemi yürütmeye devam eder; Yeni işlem, konsola veya klavyeye erişim olmadan arka planda çalıştırılır. Yeni işlem `_cwait` için yapılan çağrılar başarısız olur (zaman `_spawn`uyumsuz).  |

`cmdname` Bağımsız değişkeni, yeni işlem olarak yürütülen dosyayı belirtir ve tam yolu (kökten), kısmi yolu (geçerli çalışma dizininden) veya yalnızca bir dosya adını belirtebilir. Dosya adı uzantısına sahip değilse veya nokta (.) ile bitmezse `_spawn` , işlev önce. com dosya adı uzantısını ve ardından. exe dosya adı uzantısını,. bat dosya adı uzantısını ve son olarak. cmd dosya adı uzantısını dener. `cmdname`

Bir dosya adı uzantısına sahipse,yalnızcaouzantıkullanılır.`cmdname` Bir noktayla `_spawn` biterdiğinde, çağrı dosya adı uzantısı `cmdname` olmadan arar. `cmdname` `cmdname` `_spawnlpe` ,,Ve`_spawnvpe` işlevleri, ortam`PATH` değişkeni tarafından belirtilen dizinlerde (aynı yordamları kullanarak) arama yapın. `_spawnvp` `_spawnlp`

Bir sürücü belirticisi veya eğik çizgi `_spawn` içeriyorsa(yani,görelibiryolise),çağrıyalnızcabelirtilendosyaiçinaramayapar;yolaramayapılmaz.`cmdname`

Geçmişte, bu işlevlerden bazıları başarılı ' de sıfır `errno` olarak ayarlanmıştır; geçerli davranış C standardı tarafından belirtildiği gibi, `errno` başarılı olarak dokunulmadan bırakılmamalıdır. Eski davranışa benzemeniz gerekiyorsa, bu işlevleri çağırmadan hemen `errno` önce sıfır olarak ayarlayın.

> [!NOTE]
>  Doğru kaplama başlatma ve sonlandırmayı sağlamak için, `setjmp` veya `longjmp` işlevini kullanarak bir kaplama yordamı girmeyin veya bırakmayın.

## <a name="arguments-for-the-spawned-process"></a>Oluşturulan Işlem için bağımsız değişkenler

Bağımsız değişkenleri yeni işleme geçirmek için, `_spawn` çağrıdan bağımsız değişken olarak karakter dizelerine bir veya daha fazla işaretçi verin. Bu karakter dizeleri oluşturulan işlemin bağımsız değişken listesini oluşturur. Yeni işlem için bağımsız değişken listesini oluşturan dizelerin Birleşik uzunluğu 1024 baytı aşmamalıdır. Her bir dizenin Sonlandırıcı null karakteri (' \ 0 ') sayıma dahil değildir, ancak boşluk karakterleri (ayrı bağımsız değişkenlere otomatik olarak eklenir) dahil edilir.

> [!NOTE]
>  Dizelerde eklenen boşluklar beklenmeyen davranışlara neden olabilir; Örneğin, dizenin `"hi there"` geçirilmesi `_spawn` yeni `"hi"` işlemin iki bağımsız değişken `"there"`elde edilmesine neden olur. Amaç yeni işlemin "Merhaba." adlı bir dosyayı açma süreciydi, işlem başarısız olur. Bunu, dizeyi tırnak içine alarak önleyebilirsiniz: `"\"hi there\""`.

> [!IMPORTANT]
>  Kullanıcı girişini, içeriği açıkça denetlenmeden öğesine `_spawn` geçirmeyin. `_spawn`, bir [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw) çağrısının oluşmasına neden olacak şekilde, nitelenmemiş yol adlarının olası güvenlik açıklarına yol açabileceğini aklınızda bulundurun.

Bağımsız `_spawnl`değişken işaretçilerini ayrı bağımsız değişkenler olarak ( `_spawnle` `_spawnlp`,, ve `_spawnlpe`içinde `_spawnvpe` `_spawnv` `_spawnve`) veya işaretçiler dizisi olarak geçirebilirsiniz ( ,,ve).`_spawnvp` Oluşturulan işleme en az bir bağımsız değişken `arg0` veya `argv`[0] geçirmeniz gerekir. Kurala göre, bu bağımsız değişken programın komut satırına yazdığınız addır. Farklı bir değer hata oluşturmaz.

,, Ve çağrıları`_spawnlpe` genellikle bağımsız değişken sayısının önceden bilinen olduğu durumlarda kullanılır. `_spawnle` `_spawnl` `_spawnlp` Bağımsız değişkeni genellikle bir `cmdname`işaretçisidir. `arg0` `arg1` İle`argn` bağımsız değişkenler, yeni bağımsız değişken listesini oluşturan karakter dizelerinin işaretçileridir. Aşağıda `argn`, bağımsız değişken listesinin sonunu işaretlemek için bir **null** işaretçi olması gerekir.

,, `_spawnve`, Ve çağrıları,yeniişlemdedeğişkensayıdabağımsızdeğişkenolduğundafaydalıdır.`_spawnvpe` `_spawnvp` `_spawnv` Bağımsız değişkenlerin işaretçileri dizi `argv`olarak geçirilir *.* [0 `argv`] bağımsız değişkeni, genellikle gerçek moddaki bir yol işaretçisi veya korunan moddaki program adı ile [1] ile [`n`] arasında `argv` `argv`, yeni bağımsız değişken listesini oluşturan karakter dizelerine yönelik işaretçilerdir. [ `argv`+`n` 1] bağımsız değişkeni, bağımsız değişken listesinin sonunu işaretlemek için bir **null** işaretçi olmalıdır.

## <a name="environment-of-the-spawned-process"></a>Oluşturulan Işlemin ortamı

Bir `_spawn` çağrı yapıldığında açık olan dosyalar yeni işlemde açık kalır. ,, Ve`_spawnvp` çağrılarında, yeni işlem çağıran işlemin ortamını devralır. `_spawnl` `_spawnlp` `_spawnv` Bir ortam ayarları listesini `_spawnle` `_spawnve` `_spawnvpe` `_spawnlpe` bağımsız`envp` değişken aracılığıyla geçirerek yeni işlem için ortamı değiştirmek üzere,, ve çağrılarını kullanabilirsiniz. Bağımsız değişkeni `envp` , bir ortam değişkenini tanımlayan null ile sonlandırılmış bir dizeye işaret eden, her öğe (Final öğesi hariç) bir karakter işaretçileri dizisidir. Bu tür bir dize genellikle bir ortam `NAME` değişkeninin `NAME` adı olduğu ve `value` söz konusu değişkenin ayarlandığı dize değerinin bulunduğu biçimdedir =. `value` (Çift tırnak `value` işareti içine alınmadığını unutmayın.) `envp` Dizinin son öğesi **null**olmalıdır. Kendisi null olduğunda, oluşturulan işlem üst işlemin ortam ayarlarını devralır. `envp`

`_spawn` İşlevler, çeviri modu dahil olmak üzere açık dosyalarla ilgili tüm bilgileri yeni işleme geçirebilir. Bu bilgiler, ortamdaki `C_FILE_INFO` giriş aracılığıyla gerçek modda geçirilir. Başlangıç kodu normalde bu girişi işler ve sonra ortamdan siler. Ancak, bir `_spawn` işlev C olmayan bir işleme giriş içeriyorsa, bu girdi ortamda kalır. Ortam bilgileri, gerçek modda ikili biçimde geçirildiğinden, ortamın yazdırılması Bu girdinin tanım dizesinde grafik karakterlerini gösterir. Normal işlemler üzerinde başka bir etkiye sahip olmamalıdır. Korumalı modda, ortam bilgileri metin biçiminde geçirilir ve bu nedenle grafik karakteri içermez.

Bir işlevi çağırmadan önce herhangi bir `fflush` akışı `_flushall`açık bir `_spawn` şekilde boşaltıp (veya kullanarak) veya kapatmanız gerekir.

`_spawn` Yordamlara yapılan çağrılar tarafından oluşturulan yeni süreçler, sinyal ayarlarını korumaz. Bunun yerine, oluşturulan işlem sinyal ayarlarını varsayılana sıfırlar.

## <a name="redirecting-output"></a>Çıktıyı yeniden yönlendirme

Bir dll veya GUI `_spawn` uygulamasından arama yapıyorsanız ve çıktıyı bir kanala yönlendirmek istiyorsanız iki seçeneğiniz vardır:

- Win32 API kullanarak bir kanal oluşturun, ardından [AllocConsole](/windows/console/allocconsole)'u çağırın, başlangıç yapısındaki tanıtıcı değerlerini ayarlayın ve [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw)çağırın.

- Bir kanal oluşturacak ve **cmd. exe/c** (ya da **Command. exe/c**) kullanarak uygulamayı çağıracağı [_popen, _wpopen öğesini](../c-runtime-library/reference/popen-wpopen.md) çağırın.

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
