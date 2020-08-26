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
ms.openlocfilehash: 2f6aa420d7e6bb736721c4a68ff6451121da26ab
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840420"
---
# <a name="_spawn-_wspawn-functions"></a>_spawn, _wspawn İşlevleri

İşlevlerin her biri `_spawn` Yeni bir işlem oluşturur ve yürütür:

:::row:::
   :::column span="":::
      [_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)\
      [_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)\
      [_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)\
      [_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)\
   :::column-end:::
   :::column span="":::
      [_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)\
      [_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)\
      [_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)\
      [_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)\
   :::column-end:::
:::row-end:::

İşlev adının sonundaki harfler çeşitlemesi tespit edin.

|Harfi|Değişken|
|-|-|
| `e`  | `envp`, ortam ayarlarına işaretçiler dizisi yeni işleme geçirilir.  |
| `l`  | Komut satırı bağımsız değişkenleri işleve tek tek geçirilir `_spawn` . Bu sonek genellikle yeni bir işleme yönelik bir dizi parametre önceden bilindiğinde kullanılır.  |
| `p`  | `PATH` yürütülecek dosyayı bulmak için ortam değişkeni kullanılır.  |
| `v`  | `argv`, komut satırı bağımsız değişkenlerine işaretçiler dizisi `_spawn` işlevine geçirilir. Bu sonek genellikle yeni bir işleme yönelik bir dizi parametrenin değişken olduğu durumlarda kullanılır.  |

## <a name="remarks"></a>Açıklamalar

`_spawn`İşlevlerin her biri yeni bir işlem oluşturur ve yürütür. Çok baytlı karakter dizisi bağımsız değişkenlerini uygun şekilde otomatik olarak işler ve çok baytlı karakter dizilerini kullanımda olan çok baytlı kod sayfasına göre tanıyor. `_wspawn`İşlevleri işlevlerinin geniş karakterli sürümleridir `_spawn` ; çok baytlı karakter dizelerini işlemez. Aksi takdirde, `_wspawn` işlevler karşılıklarıyla aynı şekilde davranır `_spawn` .

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

Yeni işlemi yüklemek ve yürütmek için yeterli bellek kullanılabilir olmalıdır. `mode`Bağımsız değişkeni, çağıran işlem tarafından ve sırasında gerçekleştirilecek eylemi belirler `_spawn` . İçin aşağıdaki değerler, `mode` Process. h içinde tanımlanmıştır:

|Değer|Açıklama|
|-|-|
| `_P_OVERLAY`  | Çağıran işlemi yok etme, çağırma işlemini yok etme ( `_exec` çağrılarla aynı etkiyi).  |
| `_P_WAIT`  | Yeni işlemin yürütülmesi tamamlanana kadar çağıran bir iş parçacığını askıya alır (zaman uyumlu `_spawn` ).  |
| `_P_NOWAIT` veya `_P_NOWAITO`  | Yeni işlemle (zaman uyumsuz) bir arama işlemini eşzamanlı olarak yürütmeye devam eder `_spawn` .  |
| `_P_DETACH`  | Çağıran işlemi yürütmeye devam eder; Yeni işlem, konsola veya klavyeye erişim olmadan arka planda çalıştırılır. Yeni işlem için yapılan çağrılar `_cwait` başarısız olur (zaman uyumsuz `_spawn` ).  |

`cmdname`Bağımsız değişkeni, yeni işlem olarak yürütülen dosyayı belirtir ve tam yolu (kökten), kısmi yolu (geçerli çalışma dizininden) veya yalnızca bir dosya adını belirtebilir. `cmdname`Dosya adı uzantısına sahip değilse veya nokta (.) ile bitmezse, `_spawn` işlev önce. com dosya adı uzantısını ve ardından. exe dosya adı uzantısını,. bat dosya adı uzantısını ve son olarak. cmd dosya adı uzantısını dener.

`cmdname`Bir dosya adı uzantısına sahipse, yalnızca o uzantı kullanılır. `cmdname`Bir noktayla biterdiğinde, `_spawn` çağrı `cmdname` dosya adı uzantısı olmadan arar. `_spawnlp`,, `_spawnlpe` `_spawnvp` Ve işlevleri, `_spawnvpe` `cmdname` ortam değişkeni tarafından belirtilen dizinlerde (aynı yordamları kullanarak) arama yapın `PATH` .

`cmdname`Bir sürücü belirticisi veya eğik çizgi içeriyorsa (yani, göreli bir yol ise), `_spawn` çağrı yalnızca belirtilen dosya için arama yapar; yol arama yapılmaz.

Geçmişte, bu işlevlerden bazıları `errno` başarılı ' de sıfır olarak ayarlanmıştır; geçerli davranış `errno` C standardı tarafından belirtildiği gibi, başarılı olarak dokunulmadan bırakılmamalıdır. Eski davranışa benzemeniz gerekiyorsa, `errno` Bu işlevleri çağırmadan hemen önce sıfır olarak ayarlayın.

> [!NOTE]
> Doğru kaplama başlatma ve sonlandırmayı sağlamak için, `setjmp` veya `longjmp` işlevini kullanarak bir kaplama yordamı girmeyin veya bırakmayın.

## <a name="arguments-for-the-spawned-process"></a>Oluşturulan Işlem için bağımsız değişkenler

Bağımsız değişkenleri yeni işleme geçirmek için, çağrıdan bağımsız değişken olarak karakter dizelerine bir veya daha fazla işaretçi verin `_spawn` . Bu karakter dizeleri oluşturulan işlemin bağımsız değişken listesini oluşturur. Yeni işlem için bağımsız değişken listesini oluşturan dizelerin Birleşik uzunluğu 1024 baytı aşmamalıdır. Her bir dizenin Sonlandırıcı null karakteri (' \ 0 ') sayıma dahil değildir, ancak boşluk karakterleri (ayrı bağımsız değişkenlere otomatik olarak eklenir) dahil edilir.

> [!NOTE]
> Dizelerde eklenen boşluklar beklenmeyen davranışlara neden olabilir; Örneğin, dizenin geçirilmesi `_spawn` `"hi there"` yeni işlemin iki bağımsız değişken elde edilmesine neden olur `"hi"` `"there"` . Amaç yeni işlemin "Merhaba." adlı bir dosyayı açma süreciydi, işlem başarısız olur. Bunu, dizeyi tırnak içine alarak önleyebilirsiniz: `"\"hi there\""` .

> [!IMPORTANT]
> Kullanıcı girişini `_spawn` , içeriği açıkça denetlenmeden öğesine geçirmeyin. `_spawn` , bir [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw) çağrısının oluşmasına neden olacak şekilde, nitelenmemiş yol adlarının olası güvenlik açıklarına yol açabileceğini aklınızda bulundurun.

Bağımsız değişken işaretçilerini ayrı bağımsız değişkenler olarak (,, `_spawnl` `_spawnle` ve içinde `_spawnlp` `_spawnlpe` ) veya işaretçiler dizisi olarak geçirebilirsiniz (,, `_spawnv` `_spawnve` `_spawnvp` ve `_spawnvpe` ). Oluşturulan işleme en az bir bağımsız değişken `arg0` veya `argv` [0] geçirmeniz gerekir. Kurala göre, bu bağımsız değişken programın komut satırına yazdığınız addır. Farklı bir değer hata oluşturmaz.

`_spawnl`,, `_spawnle` `_spawnlp` Ve `_spawnlpe` çağrıları genellikle bağımsız değişken sayısının önceden bilinen olduğu durumlarda kullanılır. `arg0`Bağımsız değişkeni genellikle bir işaretçisidir `cmdname` . İle bağımsız değişkenler, `arg1` `argn` yeni bağımsız değişken listesini oluşturan karakter dizelerinin işaretçileridir. Aşağıda `argn` , bağımsız değişken listesinin sonunu işaretlemek için bir **null** işaretçi olması gerekir.

`_spawnv`,, `_spawnve` , `_spawnvp` Ve `_spawnvpe` çağrıları, yeni işlemde değişken sayıda bağımsız değişken olduğunda faydalıdır. Bağımsız değişkenlerin işaretçileri dizi olarak geçirilir `argv` *.* `argv`[0] bağımsız değişkeni, genellikle gerçek moddaki bir yol işaretçisi veya korunan moddaki program adı ile [ `argv` 1] ile `argv` [] arasında, `n` yeni bağımsız değişken listesini oluşturan karakter dizelerine yönelik işaretçilerdir. `argv`[ `n` + 1] bağımsız değişkeni, bağımsız değişken listesinin sonunu işaretlemek Için bir **null** işaretçi olmalıdır.

## <a name="environment-of-the-spawned-process"></a>Oluşturulan Işlemin ortamı

Bir çağrı yapıldığında açık olan dosyalar `_spawn` Yeni işlemde açık kalır. ,, `_spawnl` `_spawnlp` `_spawnv` Ve `_spawnvp` çağrılarında, yeni işlem çağıran işlemin ortamını devralır. `_spawnle` `_spawnlpe` `_spawnve` `_spawnvpe` Bir ortam ayarları listesini bağımsız değişken aracılığıyla geçirerek yeni işlem için ortamı değiştirmek üzere,, ve çağrılarını kullanabilirsiniz `envp` . Bağımsız değişkeni `envp` , bir ortam değişkenini tanımlayan null ile sonlandırılmış bir dizeye işaret eden, her öğe (Final öğesi hariç) bir karakter işaretçileri dizisidir. Bu tür bir dize genellikle `NAME` = `value` `NAME` bir ortam değişkeninin adı olduğu ve `value` söz konusu değişkenin ayarlandığı dize değerinin bulunduğu biçimdedir. ( `value` Çift tırnak işareti içine alınmadığını unutmayın.) Dizinin son öğesi `envp` **null**olmalıdır. `envp`Kendisi **null**olduğunda, oluşturulan işlem üst işlemin ortam ayarlarını devralır.

`_spawn`İşlevler, çeviri modu dahil olmak üzere açık dosyalarla ilgili tüm bilgileri yeni işleme geçirebilir. Bu bilgiler, ortamdaki giriş aracılığıyla gerçek modda geçirilir `C_FILE_INFO` . Başlangıç kodu normalde bu girişi işler ve sonra ortamdan siler. Ancak, bir `_spawn` Işlev C olmayan bir işleme giriş içeriyorsa, bu girdi ortamda kalır. Ortam bilgileri, gerçek modda ikili biçimde geçirildiğinden, ortamın yazdırılması Bu girdinin tanım dizesinde grafik karakterlerini gösterir. Normal işlemler üzerinde başka bir etkiye sahip olmamalıdır. Korumalı modda, ortam bilgileri metin biçiminde geçirilir ve bu nedenle grafik karakteri içermez.

`fflush` `_flushall` Bir işlevi çağırmadan önce herhangi bir akışı açık bir şekilde boşaltıp (veya kullanarak) veya kapatmanız gerekir `_spawn` .

Yordamlara yapılan çağrılar tarafından oluşturulan yeni süreçler, `_spawn` sinyal ayarlarını korumaz. Bunun yerine, oluşturulan işlem sinyal ayarlarını varsayılana sıfırlar.

## <a name="redirecting-output"></a>Çıktıyı yeniden yönlendirme

`_spawn`BIR DLL veya GUI uygulamasından arama yapıyorsanız ve çıktıyı bir kanala yönlendirmek istiyorsanız iki seçeneğiniz vardır:

- Win32 API kullanarak bir kanal oluşturun, ardından [AllocConsole](/windows/console/allocconsole)'u çağırın, başlangıç yapısındaki tanıtıcı değerlerini ayarlayın ve [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw)çağırın.

- [_Popen çağırın, _wpopen](../c-runtime-library/reference/popen-wpopen.md) bir kanal oluşturur ve **cmd.exe/c** (veya **command.exe/c**) kullanarak uygulamayı çağırır.

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

[İşlem ve ortam denetimi](../c-runtime-library/process-and-environment-control.md)<br/>
[durdur](../c-runtime-library/reference/abort.md)<br/>
[atexit](../c-runtime-library/reference/atexit.md)<br/>
[_exec, _wexec Işlevleri](../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_flushall](../c-runtime-library/reference/flushall.md)<br/>
[_getmbcp](../c-runtime-library/reference/getmbcp.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)<br/>
[_setmbcp](../c-runtime-library/reference/setmbcp.md)<br/>
[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)
