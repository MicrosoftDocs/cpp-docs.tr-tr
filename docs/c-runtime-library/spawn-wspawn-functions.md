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
ms.openlocfilehash: a22f5b0c401dd888bbda451504e644557294544d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322967"
---
# <a name="_spawn-_wspawn-functions"></a>_spawn, _wspawn İşlevleri

Işlevlerin `_spawn` her biri yeni bir işlem oluşturur ve yürütür:

|||
|-|-|
|[_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|[_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|
|[_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|[_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|
|[_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|[_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|
|[_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|[_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|

Işlev adının sonundaki harfler varyasyonu belirler.

|Harfi|Değişken|
|-|-|
| `e`  | `envp`, ortam ayarlarına işaretçiler dizisi, yeni bir işleme geçirilir.  |
| `l`  | Komut satırı bağımsız değişkenleri `_spawn` tek tek işlemeye geçirilir. Bu sonek genellikle yeni bir işlem için bir dizi parametre önceden bilindiğinde kullanılır.  |
| `p`  | `PATH`çevre değişkeni yürütmek için dosyayı bulmak için kullanılır.  |
| `v`  | `argv`, komut satırı bağımsız değişkenlerine işaretçiler `_spawn` dizisi, işleve geçirilir. Bu sonek genellikle yeni bir işlem için parametre bir dizi değişken olduğunda kullanılır.  |

## <a name="remarks"></a>Açıklamalar

Her `_spawn` biri yeni bir işlem oluşturur ve yürütür. Çok bayt karakterli dize bağımsız değişkenlerini uygun şekilde işlerler ve şu anda kullanılmakta olan çok bayt kod sayfasına göre çok bayt karakter dizilerini algılarlar. Fonksiyonlar `_wspawn` işlevlerin `_spawn` geniş karakterli sürümleridir; çok bayt karakterli dizeleri işlemez. Aksi takdirde, `_wspawn` işlevler muadillerine `_spawn` aynı şekilde çalışır.

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

Yeni işlemi yüklemek ve yürütmek için yeterli bellek kullanılabilir olmalıdır. Bağımsız `mode` değişken, önce ve sırasında `_spawn`arama işlemi tarafından gerçekleştirilen eylemi belirler. Process.h'de aşağıdaki değerler `mode` tanımlanır:

|||
|-|-|
| `_P_OVERLAY`  | Arama işlemini yeni bir işlemle yerle bir eder `_exec` ve arama işlemini yok eder (aramalarla aynı efekt).  |
| `_P_WAIT`  | Yeni işlem tamamlanana kadar bir arama iş parçacığı `_spawn`askıya (senkron).  |
| `_P_NOWAIT` veya `_P_NOWAITO`  | Yeni işlemle eş zamanlı olarak bir arama işlemi `_spawn`yürütmeye devam eder (asynchronous).  |
| `_P_DETACH`  | Arama işlemini yürütmeye devam ediyor; yeni işlem arka planda konsola veya klavyeye erişim olmadan çalıştırılır. Yeni `_cwait` işleme karşı çağrılar başarısız (asynchronous). `_spawn`  |

Bağımsız `cmdname` değişken, yeni işlem olarak yürütülen dosyayı belirtir ve tam bir yol (kökten), kısmi bir yol (geçerli çalışma dizininden) veya yalnızca bir dosya adı belirtebilir. Dosya `cmdname` adı uzantısı yoksa veya bir dönemle (.) `_spawn` bitmiyorsa, işlev önce .com dosya adı uzantısını ve ardından .exe dosya adı uzantısını, .bat dosya adı uzantısını ve son olarak .cmd dosya adı uzantısını dener.

Dosya `cmdname` adı uzantısı varsa, yalnızca bu uzantı kullanılır. Bir `cmdname` dönemle biterse, `_spawn` arama, dosya adı uzantısı olmadan arama yı arar. `cmdname` Çevre `_spawnlp` `_spawnlpe`değişkeni `_spawnvpe` tarafından `PATH` belirtilen `cmdname` dizinlerde (aynı yordamları kullanarak) arama , `_spawnvp`, ve işlevler.

Sürücü `cmdname` belirtici veya herhangi bir kesik içeriyorsa (yani göreceli bir `_spawn` yolsa), arama yalnızca belirtilen dosyayı arar; hiçbir yol arama yapılır.

Geçmişte, bu işlevlerin bazıları `errno` başarı sıfıra ayarlanmış; geçerli davranış, C `errno` standardında belirtildiği gibi başarıya dokunulmamış bırakmaktır. Eski davranışı taklit etmeniz gerekiyorsa, `errno` bu işlevleri aramadan hemen önce sıfıra ayarlayın.

> [!NOTE]
> Uygun bindirme başlatma ve sonlandırma sağlamak `setjmp` için, bir bindirme yordamı girmek veya bırakmak için veya `longjmp` işlevi kullanmayın.

## <a name="arguments-for-the-spawned-process"></a>Yumurtlama Süreci için Argümanlar

Bağımsız değişkenleri yeni işleme geçirmek için, `_spawn` çağrıdaki bağımsız değişkenler olarak karakter dizeleri için bir veya daha fazla işaretçi verin. Bu karakter dizeleri, yumurtlanan işlem için bağımsız değişken listesini oluşturur. Yeni işlem için bağımsız değişken listesini oluşturan dizelerin birleştirilmiş uzunluğu 1024 baytı geçmemelidir. Her dize için sonlandırıcı null karakter ('\0') sayıya dahil edilmez, ancak boşluk karakterleri (ayrı bağımsız değişkenlere otomatik olarak eklenir) dahildir.

> [!NOTE]
> Dizeleri katıştırılmış boşluklar beklenmeyen davranışlara neden olabilir; `_spawn` örneğin, dize `"hi there"` geçen yeni işlem iki bağımsız `"hi"` değişken `"there"`almak neden olur ve . Amaç, yeni işlemin "merhaba there" adlı bir dosyayı açmasıiçin olsaydı, işlem başarısız olur. Dize alıntı yaparak bu önleyebilirsiniz: `"\"hi there\""`.

> [!IMPORTANT]
> İçeriğini açıkça `_spawn` denetlemeden kullanıcı girişini geçirmeyin. `_spawn`createprocess için bir [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw) çağrı yla sonuçlanır, böylece niteliksiz yol adlarının olası güvenlik açıklarına yol açabileceğini unutmayın.

Bağımsız değişken işaretçileri ayrı bağımsız `_spawnl` `_spawnle`değişkenler (içinde , , `_spawnlp`, `_spawnlpe`ve `_spawnv` `_spawnve`) veya işaretçiler dizisi olarak (in , , `_spawnvp`, ve `_spawnvpe`) olarak geçirebilirsiniz. En az bir bağımsız `arg0` değişkeni veya `argv`[0], yumurtlama işlemine geçirmeniz gerekir. Bu bağımsız değişken, komut satırına yazdığınız gibi, bu bağımsız değişken programın adıdır. Farklı bir değer hata üretmez.

, `_spawnl` `_spawnle`, `_spawnlp`, `_spawnlpe` ve aramalar genellikle bağımsız değişken sayısının önceden bilindiği durumlarda kullanılır. `arg0` Bağımsız değişken genellikle `cmdname`bir işaretçi . Bağımsız `arg1` `argn` değişkenler, yeni bağımsız değişken listesini oluşturan karakter dizeleri işaretçileridir. Ardından, `argn`bağımsız değişken listesinin sonunu işaretlemek için bir **NULL** işaretçisi olmalıdır.

Yeni `_spawnv` `_spawnve`işlem `_spawnvp`için `_spawnvpe` değişken sayıda bağımsız değişken olduğunda , , ve çağrılar yararlıdır. Bağımsız değişkenlere işaretçiler bir dizi `argv`olarak geçirilir. *.* Bağımsız `argv`değişken [0] genellikle gerçek modda bir yola veya korumalı modda program adına işaretçidir ve `argv`[1] ile [ ] `argv``n`yeni bağımsız değişken listesini oluşturan karakter dizeleri işaretçileridir. [`n` `argv`+1] bağımsız değişken listesinin sonunu işaretlemek için **null** işaretçisi olmalıdır.

## <a name="environment-of-the-spawned-process"></a>Yumurtlama Sürecinin Ortamı

`_spawn` Arama yapıldığında açık olan dosyalar yeni işlemde açık kalır. `_spawnl`Yeni işlem, `_spawnv` `_spawnvp` `_spawnlp`arama işleminin ortamını devralır. `envp` Bağımsız değişken aracılığıyla `_spawnve`ortam `_spawnvpe` ayarlarının bir listesini geçirerek yeni işlem için ortamı değiştirmek için `_spawnle`, , `_spawnlpe`ve çağrıları kullanabilirsiniz. Bağımsız `envp` değişken, bir ortam değişkenini tanımlayan null-sonlandırılan dizeişareteden her öğe (son öğe hariç) karakter işaretçileri dizisidir. Böyle bir dize `NAME` = `value` genellikle `NAME` bir ortam değişkeninin `value` adı olan forma sahiptir ve bu değişkenin ayarlandığı dize değeridir. (Çift `value` tırnak işaretlerine dahil olmayana dikkat edin.) `envp` Dizinin son öğesi **NULL**olmalıdır. Kendisi `envp` **NULL**olduğunda, yumurtlanan işlem üst işlemin ortam ayarlarını devralır.

Işlevler, `_spawn` çeviri modu da dahil olmak üzere açık dosyalarla ilgili tüm bilgileri yeni işleme aktarabilir. Bu bilgiler, ortama `C_FILE_INFO` giriş yoluyla gerçek modda geçirilir. Başlangıç kodu normalde bu girişi işler ve sonra ortamdan siler. Ancak, bir `_spawn` işlev C olmayan bir işlem ortaya çıkarsa, bu giriş ortamda kalır. Ortam bilgisi gerçek modda ikili biçimde geçirildiği için ortam yazdırma, bu giriş için tanım dizesinde grafik karakterlerini gösterir. Normal işlemler üzerinde başka bir etkisi olmamalıdır. Korumalı modda, ortam bilgileri metin biçiminde aktarılır ve bu nedenle grafik karakteri içermez.

Bir işlevi aramadan `fflush` önce `_flushall`herhangi bir `_spawn` akışı açıkça temizlemeniz (kullanmanız veya) kapatmanız gerekir.

`_spawn` Yordamlara yapılan çağrılar tarafından oluşturulan yeni işlemler sinyal ayarlarını korumaz. Bunun yerine, oluşturulan işlem sinyal ayarlarını varsayılan olarak sıfırlar.

## <a name="redirecting-output"></a>Çıktıyı Yönlendirme

Bir DLL `_spawn` veya GUI uygulamasından arıyorsanız ve çıktıyı bir pipeye yönlendirmek istiyorsanız, iki seçeneğiniz vardır:

- Bir boru oluşturmak için Win32 API'sını kullanın, ardından [AllocConsole'u](/windows/console/allocconsole)arayın, başlangıç yapısındaki tutamaç değerlerini ayarlayın ve [CreateProcess'i](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw)arayın.

- Bir boru oluşturacak _wpopen [_popen](../c-runtime-library/reference/popen-wpopen.md) arayın ve **cmd.exe /c** (veya **command.exe /c)** kullanarak uygulamayı çağırın.

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
[Iptal](../c-runtime-library/reference/abort.md)<br/>
[atexit](../c-runtime-library/reference/atexit.md)<br/>
[_exec, _wexec Fonksiyonlar](../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_flushall](../c-runtime-library/reference/flushall.md)<br/>
[_getmbcp](../c-runtime-library/reference/getmbcp.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)<br/>
[_setmbcp](../c-runtime-library/reference/setmbcp.md)<br/>
[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)
